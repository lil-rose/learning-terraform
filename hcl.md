# Hashicorp COnfiguration Language

aka Terraform language

## Basics

Terraform code is written in the **HashiCorp Configuration Language** (HCL) in files with the extension .tf

The main purpose of the Terraform language is declaring resources, which represent infrastructure objects.

The first step to using Terraform is typically to configure the provider(s) you want to use.

Example with AWS:
```terraform
provider "aws" {
region = "us-east-2"
}
```

Example with Kubernetes:
```terraform
terraform {
  required_providers {
    kubernetes = {
      source  = "hashicorp/kubernetes"
    #   version = ">= 2.0.0"
    }
  }
}
provider "kubernetes" {
  config_path = "~/.kube/config"
}
```

With only Docker:
```terraform
terraform {
  required_providers {
    docker = {
      source = "kreuzwerker/docker"
    }
  }
}
provider "docker" {}
```

## Resources

For each type of provider, there are many different kinds of resources that you can create, such as servers, databases, and load balancers. The general syntax for creating a resource in Terraform is:

```terraform
resource "<PROVIDER>_<TYPE>" "<NAME>" {
  [CONFIG ...]
}
```

Example using Kubernetes:
```terraform
resource "kubernetes_namespace" "test" {
  metadata {
    name = "nginx"
  }
}
```
- PROVIDER = kubernetes
- TYPE = namespace
- NAME = test
- the rest is config

