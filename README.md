# try-aws-batch-on-fargate

AWS Batch on Fargate を試してみる。  
AWS Batch on EC2 も作成し比較してみる。  

## AWS Batch on EC2

### CFn スタック 作成

```sh
vpc_id=vpc-xxxxxxxx
subnet_ids=subnet-xxxxxxxx,subnet-xxxxxxxx

aws cloudformation deploy \
    --template-file aws-batch-on-ec2.cfn-template.yml \
    --stack-name aws-batch-on-ec2 \
    --capabilities CAPABILITY_NAMED_IAM \
    --parameter-overrides VpcId=$vpc_id SubnetIds=$subnet_ids
```

### CFn スタック 削除

```sh
aws cloudformation delete-stack \
    --stack-name aws-batch-on-ec2
```

## AWS Batch on Fargate

### CFn スタック 作成

```sh
vpc_id=vpc-xxxxxxxx
subnet_ids=subnet-xxxxxxxx,subnet-xxxxxxxx

aws cloudformation deploy \
    --template-file aws-batch-on-fargate.cfn-template.yml \
    --stack-name aws-batch-on-fargate \
    --capabilities CAPABILITY_NAMED_IAM \
    --parameter-overrides VpcId=$vpc_id SubnetIds=$subnet_ids
```

### CFn スタック 削除

```sh
aws cloudformation delete-stack \
    --stack-name aws-batch-on-fargate
```
