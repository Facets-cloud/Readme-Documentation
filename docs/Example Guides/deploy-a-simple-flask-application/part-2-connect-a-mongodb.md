---
title: Part 2 - Connect a MongoDB
excerpt: Deploying a Mongodb and connecting the flask app to mongodb.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
In the second part of this demo, we are going to modify our flask app to connect and interact with MongoDB.

Through this intent, Facets automatically provisions the MongoDB, provides required accesses to MongoDB from the app as well as automatically creates credentials and makes it available through environment variables to the application.

Below are the steps we will follow to deploy MongoDB and interact with it from within our application.

# Step 1: - Modify the application to connect to MongoDB

We will modify our flask application to interact with MongoDB. We create a new route called <code>/det</code> and pass a query parameter named <code>text</code> which will create a new record every time it is navigated and then displays all the records in a particular MongoDB collection. Each record is a simple json with 2 keys called <code>Random\_Number</code> and <code>Your\_text</code>. The value of the first key is a random integer between <code>1000</code> and <code>1000000</code>. The value of the second key is the text that you passed as a query parameter.

1. Modify the python code 

```python
from http import client
from flask import Flask,request
import os
from bson import json_util
import json
import random
from pymongo import MongoClient
app = Flask(__name__)
@app.route('/')
def hello_world():
    return 'Hello World'
@app.route('/healthz')
def healthz():
    return ''
@app.route('/det')
def det():
    text = request.args.get('text')
    client = MongoClient('mongodb://{0}:{1}@{2}'.format(os.getenv('MONGODB_USER'),os.getenv('MONGODB_PASSWORD'),os.getenv('MONGO_HOST')))
    db = client['facets']
    cl = db["demo"]
    rec = {
        "Random_Number": random.randint(1000,1000000),
        "Your_text": text
    }
    x = cl.insert_one(rec)
    cur = cl.find({})
    return json_util.dumps(cur)
 
if __name__ == '__main__':
    app.run(host='0.0.0.0')
```

2. We have used the pymongo python library. Hence, include pymongo in the <code>requirements.txt</code> along with the other dependencies already defined.

3. Rebuild the docker image and push to your control plane with a new tag

```shell
docker build -t facets-python-demo:2 .
facetsctl image push facets-demo1 app QA facets-python-demo:2 1
```

# Step 2: - Modify blueprint repository to add an instance of MongoDB

1. Create a new directory named <code>mongo/instances</code> inside <code>facets-python-demo/</code> directory.

2. Create a file named <code>facets-demo-mongo.json</code> inside instances/ directory with the following content

```json
{
    "$schema": "https://docs.facets.cloud/schemas/mongo/instances/mongo.schema",
    "name": "facets-demo-mongo",
    "k8s_service_names": [
        "facets-demo-mongo"
    ],
    "size": "S",
    "k8s_slave_service_names": []
}
```

3. Create a file named <code>sizing.json</code> inside <code>mongo/</code> directory with the following content. This file provides sizing options for mongodb.

```json
{
    "$schema": "https://docs.facets.cloud/schemas/mongo/sizing.schema",
    "S": {
        "podCPULimit": 1,
        "podMemoryLimit": 2,
        "volumeSize": 10
    }
}
```

4. Create another file named <code>disaster-recovery.json</code> at the same level as <code>sizing.json</code> with the following content. This file defines our disaster recovery configurations for the mongodb. For the purpose of this demo, we have disabled the disaster recovery. 

```json
{
    "$schema": "https://docs.facets.cloud/schemas/mongo/disaster-recovery.schema",
    "creationStrategy": {
        "triggerSchedule": []
    },
    "enabled": false,
    "retentionStrategy": {
        "incrementalWindow": {},
        "rollingWindow": {
            "days": 0,
            "hours": 0,
            "weeks": 0
        },
        "triggerSchedule": []
    }
}
```

# Step 3: - Modify <code>app.json</code> to include the dependency with MongoDB

In order for our flask application to connect to the MongoDB database, we need database credentials. Facets Control Plane automatically creates credentials and sets them as environment variables. This is done using the <code>permission</code> block in the <code>app.json</code>. Application can then simply request credentials with the set of permissions defined in the permission block. 

1. The permission block below instructs facets to create a user with read-write permission to the facets-demo-mongo database.

```json
"permission": [
      {
        "name": "facets-demo-mongo",
        "resourceType": "mongo",
        "resourceName": "facets-demo-mongo",
        "permission": "READ_WRITE"
      }
    ]
```

2. We now define environment variables in our app.json file. For this application, we use 3 environment variables namely <code>MONGODB\_USER</code>, <code>MONGODB\_PASSWORD</code> and <code>MONGO\_HOST</code>. The below block describes defining environment variables in our <code>app.json</code>.

```json
"env": {
      "MONGO_HOST": {
        "type": "static",
        "default": "facets-demo-mongo.default"
      },
      "MONGODB_USER": {
        "type": "credential",
        "permissionName": "facets-demo-mongo",
        "attribute": "userName"
      },
      "MONGODB_PASSWORD": {
        "type": "credential",
        "permissionName": "facets-demo-mongo",
        "attribute": "password"
      }
    },
```

3. Copy the below modified code in your app.json for permissions and environment variables blocks. Note - Make sure to change the image URI as well. Copy the image URI from the Artifacts tab in the control plane for the latest pushed image and replace the image URI in the code below with your URI.

```json
{
  "$schema": "https://docs.facets.cloud/schemas/application/instances/application.schema",
  "kind": "facets.modules.common.application",
  "disabled": false,
  "apiVersion": "v2",
  "metadata": {
  },
  "spec": {
    "env": {
      "MONGO_HOST": {
        "type": "static",
        "default": "facets-demo-mongo.default"
      },
      "MONGODB_USER": {
        "type": "credential",
        "permissionName": "facets-demo-mongo",
        "attribute": "userName"
      },
      "MONGODB_PASSWORD": {
        "type": "credential",
        "permissionName": "facets-demo-mongo",
        "attribute": "password"
      }
    },
    "loadbalancing": {
      "rules": [
        {
          "ingress": "ingress",
          "path": "/",
          "portName": "port5000"
        }
      ]
    },
    "permission": [
      {
        "name": "facets-demo-mongo",
        "resourceType": "mongo",
        "resourceName": "facets-demo-mongo",
        "permission": "READ_WRITE"
      }
    ],
    "release": {
      "strategy": "RollingUpdate",
      "build": {
        "image": "313496281593.dkr.ecr.us-east-1.amazonaws.com/facets/facets-demo1/app:facets8"
      }
    },
    "runtime": {
      "size": {
        "value": "small",
        "namespace": "GP"
      },
      "autoscaling": {
        "cpuThreshold": "50",
        "max": 1,
        "min": 1
      },
      "ports": [
        {
          "name": "port5000",
          "port": 5000
        }
      ]
    }
  }
}
```

4. Push all changes to your git repo

# Step 4: - Release and test the changes

1. Go to the Release tab in Facets control Plane and click Release. This will perform a complete release of all the changes in your blueprint. There is also a button called Selective which selectively releases your changes. For example, if you have multiple applications and you selectively want to release changes to only a few of them, use this option.

2. The logs for this release can be seen in Actions -> Terraform Logs.

3. Once the release is a success, navigate to the Application tab, find the application and the ingress details

4. Go to your browser and paste the ingress url. Append <code>/det?text=Hello</code> to the url and access the application. Every time you refresh the page, you should see a new row added and displayed.

:clap: If you are able to see an increase in the number of rows every time you refresh the page, it means the application is successfully deployed and able to communicate with the MongoDB.
