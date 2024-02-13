Terraform Commands:
Terraform uses the Hashicorp language (HCL)

terraform init
This will initialize terraform.

terraform plan
This will let you preview the changes that have been made, E.G. Adding resources such as EC2 instances as well as VPC, and much more

terraform apply -auto-approve
This will implement the changes that have been configured, note: to skip the “yes” prompt Use the -auto-approve

terraform state list
This will allow you to see the current states (resources) on the current configuration 

terraform show
This will display all the states  which are configured on the system.

terraform state show [resource-name] 
This will show details of a specified state (resource). The name can be found by doing terraform state list

terraform fmt 
This will format your .tf files.

terraform destroy 
This will destroy all your managed states (resources) as the name suggests.

