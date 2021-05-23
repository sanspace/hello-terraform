#### Hello Terraform

🎬 [**San**](https://sanspace.in)thosh Srinivasan

---

#### What?

  > Terraform is a tool for building, changing, and versioning infrastructure safely and efficiently.



  - Infrastructre as Code (IaC)
  - Declarative, High Level Syntax

---

#### What not?

  - A configuration management tool (chef, puppet, etc.)
  - Low level Programmatic Access (boto, fog)

---

#### Why?

  - Cloud-agnostic
  - Open Source

---

#### Install

  - [tfenv](https://github.com/tfutils/tfenv) for Linux, MacOS
  - chocolatey or direct binary download for Windows

<small>https://learn.hashicorp.com/tutorials/terraform/install-cli<small>

---

#### Configure

If you're using AWS CLI already, you're good to go.

Otherwise, set up AWS credentials.

---

#### Concepts

Declare the Resources you want, Terraform will create it for you.



  - Terraform Core
  - Terraform Configuration
  - Terraform State
  - Terraform Providers



##### Providers

> Terraform relies on plugins called "providers" to interact with remote systems.

<small>https://www.terraform.io/docs/language/providers/index.html</small>



##### Resources

> Each resource block describes one or more infrastructure objects, such as virtual networks, compute instances, or higher-level components such as DNS records.



##### State

> This state is used to map real world resources to your configuration, keep track of metadata, and to improve performance.



##### Configuration

Terraform code files that declares an infrastructure

---

#### Launch an EC2

```terraform
resource "aws_instance" "demo_server" {
  ami           = "ami-830c94e3"
  instance_type = "t2.micro"

  tags = {
    Name = "TerraformDemoInstance"
  }
}
```



```terraform
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 3.42.0"
    }
  }

  required_version = ">= 0.15.4"
}

provider "aws" {
  profile = "default"
  region  = "us-west-2"
}

resource "aws_instance" "app_server" {
  ami           = "ami-830c94e3"
  instance_type = "t2.micro"

  tags = {
    Name = "ExampleAppServerInstance"
  }
}
```

---

#### Commands

  - init
  - plan
  - apply
  - destroy



  - fmt
  - validate
  - show
  - state

---

#### Demo

# 👨‍🏫

---

#### Resources 📚

  - [Official Docs](https://github.com/sanspace/hello-terraform.git)
  - [Official Tutorial](https://learn.hashicorp.com/terraform)

  <small>*This deck uses several examples from above resources</small>

---

#### Feedback 🗣️

  - This deck is on [Github](https://github.com/sanspace/hello-terraform). Issues/PRs are appreciated!
  - Reach out to [me](https://sanspace.in).
