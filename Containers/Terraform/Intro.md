Terraform Commands
Terraform uses the Hashicorp language (HCL)

This will initialize terraform.
```
terraform init
```


This will let you preview the changes that have been made, E.G. Adding resources such as EC2 instances as well as VPC, and much more
```
terraform plan
```

This will implement the changes that have been configured, note: to skip the “yes” prompt Use the -auto-approve
```
terraform apply -auto-approve
```

This will allow you to see the current states (resources) on the current configuration 
```
terraform state list
```


This will display all the states which are configured on the system.
```
terraform show
```

This will show details of a specified state (resource). The name can be found by doing terraform state list
```
terraform state show [resource-name] 
```

This will format your .tf files.
```
terraform fmt 
```

This will destroy all your managed states (resources) as the name suggests.
```
terraform destroy 
```


