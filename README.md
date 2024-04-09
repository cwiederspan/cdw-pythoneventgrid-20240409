# cdw-pythoneventgrid-20240409
A simple repo for testing out infrastructure as code for a Python function app that is triggered by an Event Grid event.

```bash

cd ./infra
az group create -n cdw-functesting-20240409 -l eastus

az deployment group create -g cdw-functesting-20240409 --template-file main.bicep

cd ./src
func azure functionapp publish cdw-functesting-20240409-app


```