# Terraform

- [Terraform](https://www.terraform.io/)
- [Terraform Registry](https://registry.terraform.io/)
- [Learn Terraform](https://learn.hashicorp.com/terraform)
- [Prepare for the exam](https://www.hashicorp.com/certification/terraform-associate)

## Links

- [Udemy: HashiCorp Certified: Terraform Associate 2023](https://www.udemy.com/course/terraform-beginner-to-advanced/) - [Github](https://github.com/zealvora/terraform-beginner-to-advanced-resource/tree/master)
- [Terraform Best Practices](https://www.terraform-best-practices.com/)
- [tfenv](https://github.com/tfutils/tfenv) - Terraform version manager
- [Terraform Examples](https://github.com/futurice/terraform-examples) - Terraform samples for all the major clouds you can copy and paste

## Commands

```sh
terraform init
```
```sh
terraform plan
```
```sh
terraform apply
```
```sh
terraform destroy -target <provider_resource_type>.<local_resource_name>
```
```sh
terraform refresh
```
Test [built-in functions](https://developer.hashicorp.com/terraform/language/functions) in console
```sh
terraform console
```
Format a terraform file
```sh
terraform fmt
```
Debugging terraform plan
```sh
export TF_LOG_PATH=/tmp/terraform.log
```
Check terraform file if is syntactically valid
```
terraform validate
```
