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

Terraform cli [commands](https://developer.hashicorp.com/terraform/cli/commands)
```sh
terraform init
terraform plan
terraform plan -refresh=false # don't refresh state
terraform plan -out=<filename> # save terraform plan to specific file
terraform refresh
terraform apply
terraform destroy -target <provider_resource_type>.<local_resource_name>
```

```sh
```
```sh
```
```sh
```
```sh
```
Test [built-in functions](https://developer.hashicorp.com/terraform/language/functions) in console
```sh
terraform console
```

Format a Terraform file [link](https://developer.hashicorp.com/terraform/cli/commands/fmt)
```sh
terraform fmt
```

Debugging Terraform code with [environment variables](https://developer.hashicorp.com/terraform/cli/config/environment-variables)
```sh
export TF_LOG_PATH=/tmp/terraform.log
export TF_LOG=TRACE
```

Check Terraform file if is [syntactically valid](https://developer.hashicorp.com/terraform/cli/commands/validate)
```sh
terraform validate
```

[Provisioners](https://www.terraform.io/language/resources/provisioners/local-exec)
```sh
local-exec
remote-exec
null resource
on_failure
```

Implementing the standard lifecycle but takes no further action [link](https://registry.terraform.io/providers/hashicorp/null/latest/docs/resources/resource)
```sh
null_resource
```

[Terraform workspace](https://developer.hashicorp.com/terraform/language/state/workspaces)
```sh
terraform workspace -h
```
