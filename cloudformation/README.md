# Cloudformation templates to deploy Ansible Tower

## Single Node Ansible Tower

## 3 node Ansible Tower Cluster with RDS backend

- Create a stack for generating cluster internal SSH keys

```
aws cloudformation create-stack \
       --capabilities CAPABILITY_IAM \
       --stack-name cfn-secret-provider \
       --template-body file://cloudformation/cfn-resource-provider.yaml

aws cloudformation wait stack-create-complete  --stack-name cfn-secret-provider 
```

- Deploy the 3 node Ansible Tower Cluster using the tower_ha_cluster.yaml
