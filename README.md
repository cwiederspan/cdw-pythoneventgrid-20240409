# cdw-pythoneventgrid-20240409
A simple repo for testing out infrastructure as code for a Python function app that is triggered by an Event Grid event.

```bash

cd ./infra
az group create -n cdw-functesting-20240409 -l eastus

az deployment group create -g cdw-functesting-20240409 --template-file main.bicep

cd ./src
func azure functionapp publish cdw-functesting-20240409-app


```


```bash

az group create -n cdw-functesting-20240409 -l eastus

az ad sp create-for-rbac --role Contributor --scopes /subscriptions/30c417b6-b3c1-4b62-94c9-0d3a80a182e9/resourceGroups/cdw-functesting-20240409 --sdk-auth

```