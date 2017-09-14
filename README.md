# NBI Pilot

This repository contains preliminary information related to the NDS Labs National Bridge Infrastructure (NBI) data pilot.  This pilot consists of a MongoDB containing the NBI dataset and a Jupyter environment with sample notebook for use in the Labs Workbench system.

## Labs Workbench
The [Labs Workbench](https://www.workbench.nationaldataservice.org) is a service of the National Data Service (NDS). To register for an account:
* Go to https://www.workbench.nationaldataservice.org
* Select "Sign Up"
* Complete the registration form and submit "Request Access"
* You will be required to verify your email address 
* Your account will be approved by NDS staff

### NBI MongoDB in Labs Workbench
The Labs Workbench system now contains a copy of the NBI MongoDB created using the [ProjectNBI](https://github.com/kaleoyster/ProjectNBI) process.  This database contains the complete set of records (17 million) for all states. Indexes have been created on the structureNumber, stateCode, and year.

The [kubernetes](/kubernetes) directory contains the YAML file used to create the nbi-mongo instance.

### NBI Jupyter Environment
The [specs](/specs) folder contains the Labs Workbench specification for the NBI Jupyter environment.  This application has not yet been added to the official catalog. To use this environment:
* Login to [Labs Workbench](https://www.workbench.nationaldataservice.org)
* Select "Catalog"
* Select "Import"
* Paste the contents of [jupyternbi.json](jupyternbi.json)
* Select "Import" button

To run the Jupyter for NBI environment:
* In the "Catalot", select the "Jupyter for NBI" application then "Add" 
* Select "Applications" then "Launch"
* Once the application is started, select the endpoint link
* You will be prompted to enter your username/password

Once running, you can load the sample notebook from this repository.

## Docker image
The Docker image is intended for use in the NDS Labs Workbench service. The image extends the  ```jupyter/scipy-notebook``` adding matplotlib and pymongo dependencies.  To build:
```
cd docker
docker build -t craigwillis/jupyter-nbi .
```

## Jupyter notebook
The sample notebook is based on the Robin Gandhi's [example](http://faculty.ist.unomaha.edu/rgandhi/r/mongoNBI.html).

