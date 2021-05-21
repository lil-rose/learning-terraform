# Learning Terraform

My notes for learning Terraform.

This is specifically using Kubernetes, for local tests I use minikube, for learning Kubernetes I am using [this repo](https://github.com/lil-rose/learning-kubernetes).

## Terraform files

*more details [here](https://www.terraform.io/docs/language/files/index.html).*

**Terraform file**: .tf file (also refered as "configuration file").

- A module is a collection of .tf and/or .tf.json files kept together in a directory.

- Terraform evaluates all of the configuration files in a module, effectively treating the entire module as a single document.

### Modules

*More details [here](https://www.terraform.io/docs/language/modules/index.html).*

**Root module**: Module that contains .tf files on the directory were terraform is called.

**Child module**: A Terraform module that is called by another module (usualy root module) to include their resources into the configuration.

### Syntax and Terraform language

[here](hcl.md)