# README.md file formate notes:-

# Chapter-1 Heading

Headings
To create a heading, add one to six # symbols before your heading text. The number of # you use will determine the size of the heading.

# The largest heading
## The second largest heading
### The third largest heading
###### The smallest heading


# Chapter-2 Lists

Lists
You can make an unordered list by preceding - and space, see:-

- We are going to learn about different Terraform Functions using Terraform console command
- In detail, we are going to learn about `templatefile` and `concat` functions with an AWS example


# Chapter-3 distinct block

To format code or text into its own distinct block, use triple backticks, put codes/script within backticks, Noted:-here we have multiple option see:- 1st- ```  ```, 2nd- ```t ```, 3rd- ```bash ```.

1st example of text into its own distinct block
```t
# Terraform Initialize
terraform init

# Terraform Validate
terraform validate
```

2nd example of text into its own distinct block
```bash
# Terraform Plan
terraform plan

# Terraform Apply
terraform apply -auto-approve
```

3rd example of text into its own distinct block
```
# Terraform destroy
terraform destroy

# Terraform destroy
terraform destroy -auto-approve
```

-------------------------------------------------------------------

# See All in One Example Notes, where you can see & understand:-

# Terraform Functions

## Introduction-:
- We are going to learn about different Terraform Functions using Terraform console command
- In detail, we are going to learn about `templatefile` and `concat` functions with an AWS example


### outputs.tf
- Added output with `concat` function
```t
# Concat Security Group IDs in Output
output "security_group_ids" {
  description = "This will return the IDs of the security groups attached to your web instance as a list"
  value = concat([aws_security_group.vpc-ssh.id, aws_security_group.vpc-web.id])
}
/* Note: This will return the IDs of the security groups attached to your web 
instance as a list. You can use these lists as inputs in submodules.*/
```


### user_data.tmpl
- Contains the shell script which will install the package provided from terraform variables. 
```sh
#! /bin/bash
sudo yum update -y
sudo yum install -y ${package_name}
sudo yum list installed | grep ${package_name} >> /tmp/package-installed-list.txt
```


## Execute Terraform Commands:
- Verify the installed packages
```t
# Terraform Initialize
terraform init

# Terraform Validate
terraform validate

# Terraform Plan
terraform plan

# Terraform Apply
terraform apply -auto-approve

# Review Outputs for concat function
security_group_ids = [
  "sg-09f936287ddfc3b14",
  "sg-01f8a08bcbc4b9590",
]

# Connect to EC2 VM
ssh -i "private-key" ec2-user@<public_ip>
cat /tmp/package-installed-list.txt
```


## References
- [Terraform Functions](https://www.terraform.io/docs/language/functions/index.html)

---------------------------------------