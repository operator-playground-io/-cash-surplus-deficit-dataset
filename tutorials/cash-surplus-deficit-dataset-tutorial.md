---
title: Sample Python Application using cash surplus deficit dataset
description: This tutorial explains how to use cash surplus deficit dataset in a sample python application
---

### Example Application: GDP Trends Application (Python)

***Introduction***

GDP Trends Application is a Dash Application. It uses Python's Flask framework and plotly for an elegant visualization of GDP trends of South Asian countries till 2012, which is processed and pulled from an external data source using Pandas. 

***Code Structure***

![codestructure](_images/app-structure.PNG)

There are 2 folders that are of our interest:
- k8s: This contains all the deployment and service yaml for the application. This defines the deployment and exposure of our application.
- app: This contains the python application.

### Try the example

Get the application code
```execute
cd /home/student/projects && git clone https://github.com/operator-playground-io/sample-cash-surplus-deficit-dataset.git
```

Copy the dataset into application folder
```execute
cp -R /home/student/projects/cash-surplus-deficit-dataset/cash-surplus-deficit /home/student/projects/sample-cash-surplus-deficit-dataset/app/.
```

Install and start the application using skaffold tool
```execute
cd /home/student/projects/sample-cash-surplus-deficit-dataset && skaffold config set default-repo localhost:5000 && skaffold run
```

### Access the example application

Click the below URL to access the deployed applicaion.
URL :  http://##DNS.ip##:32101

### To Deploy changes to Kubernetes in Dev Mode

Go to Developer Dashboard tab, it will provide you with the IDE along with the integrated terminal.  Click on the bottom status bar and select `TERMINAL`. 

k8s folder contains all the manifest files and defines the deployment strategy for the application.
One can execute them using :
```execute
kubectl apply -f k8s/
```

In this example , we use `Skaffold` which simplifies local development. You can deploy the application is DEV mode which keeps watching for the files changes and on any change, triggers the entire deployment process automatically without the user having to run and manage it manually.

Navigate to the example:
```execute
cd /home/student/projects/sample-cash-surplus-deficit-dataset
```

Deploy the changes in dev mode:
```execute
skaffold config set default-repo localhost:5000 && skaffold dev
```

On exiting the command, Skaffold will automatically destroy all the resources it created with above command.

Also, you can use the `skaffold run` to deploy the changes onto Kubernetes as a normal mode. In this mode, the resources created remains unless the user deletes them.

### Clean up the Kubernetes resources (Example application)

You can delete all the application resources created by executing the following command:
```execute
cd /home/student/projects/sample-cash-surplus-deficit-dataset && skaffold delete
```




