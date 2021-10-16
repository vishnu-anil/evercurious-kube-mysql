## evercurious-kube-mysql
Create a Mysql server in GCP kubernetes cluster

## Prerequisites
* A valid GCP Account
* A disk of size more than your Storagesize. This can be created with below command. Remember to use "Name" for the disk same as Name in the values.yaml

```
gcloud beta compute disks create <Name>-pv-disk --project=<Your-projct> --type=pd-balanced --description=Disk\ t --size=10GB --zone=us-central1-a
```

## Configuration
| Parameter | Description | Default |
|---|---|---|
| Name | Name of the deployment or server, your service, pvc, pv etc| ecmysql|
| dbsecret | base64 encoded password | bXlyb290cGFzc3dvcmQ= |
| storagesize | Storage size of your persistent volume | 5Gi |
| storageclaim | Claiming storage size for your mysql server | 2Gi |
| image | Mysql version you want to install| 5.7 |


## Installation
```
helm install kube-mysql ./ -f values.yaml
```
