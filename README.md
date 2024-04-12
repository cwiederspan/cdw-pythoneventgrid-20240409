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

BASE_NAME=cdw-functesting-20240411

az group create -n $BASE_NAME -l eastus

az ad sp create-for-rbac -n $BASE_NAME-sp --role Contributor --scopes /subscriptions/30c417b6-b3c1-4b62-94c9-0d3a80a182e9/resourceGroups/$BASE_NAME --json-auth

# Add permissions to manage the EventGrid Subscriptions (part of the Bicep file)
az role assignment create --assignee c7ac86a5-9a3b-48d8-82e3-246d6bb5d88a \
--role 'EventGrid EventSubscription Contributor' \
--scope /subscriptions/30c417b6-b3c1-4b62-94c9-0d3a80a182e9

```