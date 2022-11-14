# terraform aws on windows
1. install terraform and add env path to the terraform.exe, check installation by
```
>terraform -help
```
2. install aws cli 
```
>aws --version
```
3. in aws console, create user & role  to get access key ID and secret access key, then assign parameters:
```
set  AWS_ACCESS_KEY_ID=
set AWS_SECRET_ACCESS_KEY=
```
4. in aws console, lauch instance with t2.micro in region 'southest-1', create key-pair "pegasus-key-pair", copy vpc_id
5. in aws console, create vpc in region 'southeast-1', copy subnets to variables.tf
6. run
```
>terraform init
>terraform fmt
>terraform validate
>terraform apply
```
7. output once completed the auto-scaling:
```
Outputs:

asg_name = "terraform-example-asg"
launch_configuration = "terraform-example-lc"
lb_name = "vpc-0772177330d0ff684-alb-118396211.ap-southeast-1.elb.amazonaws.com"
security_group = "sg-0832451d4ce120db3"
```

#ref
https://developer.hashicorp.com/terraform/tutorials/aws-get-started/aws-build
https://github.com/WarotAsawa/aws-web-example
