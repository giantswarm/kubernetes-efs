# Helm chart for 'efs-provisioner'

The Kubernetes project provides an AWS [EFS provisioner](https://github.com/kubernetes-incubator/external-storage/tree/master/aws/efs) 
that is used to fulfill PersistentVolumeClaims with EFS PersistentVolumes. This version is highly inspaired in the original but adding a pod security policy aligned with our platform patterns.

The persisent volumes are created as folders with in an AWS EFS filesystem.

  https://aws.amazon.com/efs/

## Prequisites

You must create the EFS file system firstly.

  https://docs.aws.amazon.com/efs/latest/ug/creating-using-create-fs.html

Be sured to include the security group that is used by the cluster master(s)/workers.

## Configuring

At a minimum you must the supply the EFS file system ID and the AWS region

```
helm install stable/efs-provisioner --set efsFileSystemId=fs-12345678 --set awsRegion=ue-central-1
```

All the values documented below and by `helm inspect values`.

```
helm inspect values stable/efs-provisioner
```
