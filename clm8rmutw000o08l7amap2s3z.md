---
title: "Terraform vs. Ansible:"
datePublished: Thu Sep 07 2023 06:06:42 GMT+0000 (Coordinated Universal Time)
cuid: clm8rmutw000o08l7amap2s3z
slug: terraform-vs-ansible
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694066679531/79fb2d01-c491-45e0-830b-6a597092358d.png
tags: ansible, devops, terraform, 90daysofdevops, trainwithshubham

---

**W**hen looking for an infrastructure-as-code (IaC) tool, you’ll find several options, including Terraform and Ansible. Both of these IaS tools provision infrastructure in the cloud, but they have distinct differences that make one better to use than the other in certain environments, which makes each tool more suitable than the other for certain use cases. Terraform is more of a provisioning tool, while Ansible is used for the conﬁguration of cloud infrastructure. 

# What Does Terraform Do?

Instead of manually conﬁguring cloud infrastructure (e.g., virtual machines), Terraform lets DevOps teams write conﬁguration scripts—one or more text ﬁles written in Hashicorp Control Language—that deploy resources remotely using automation. It can be used against any infrastructure for which a provider exists.

# How Does Terraform Work?

Terraform uses a conﬁguration as the reference for the desired state of infrastructure resources and ensures that the provisioned resources match what is speciﬁed in the conﬁguration. The use of its conﬁgurations ensures that infrastructure is deployed in a consistent manner. It can deploy virtual machines, network components like ﬁrewalls, database servers, and any other hardware used to run the cloud environment.

# What Does Ansible Do?

Ansible is used to conﬁgure infrastructure. After you deploy infrastructure, you might need to make changes to conﬁgurations to support new software or upgraded features. DevOps can write automation scripts to change conﬁgurations across multiple cloud resources.

# How Does Ansible Work?

When you want to automatically conﬁgure infrastructure in the cloud, it would be better to use Ansible than Terraform. Developers create YAML ﬁles to automate conﬁguration deployments in the cloud. Terraform also deploys conﬁgurations, but Ansible will let you update and change current infrastructure conﬁgurations.

Ansible works with “playbooks,” which are procedural scripts that let developers deﬁne what they want to execute on infrastructure. It works with DevOps operations to continually make changes to infrastructure as developers deploy applications.

# Terraform vs. Ansible: 3 Similarities

Although Terraform and Ansible are used for different purposes, they have some similarities. They both have orchestration capabilities that let DevOps deploy infrastructure to the cloud. While infrastructure is deployed, they both conﬁgure it at the same time to make it functional for developers or operations people.

They both work on virtual machines without installing agents on the remote infrastructure, and both work with SSH connections. Neither of them require expensive third-party infrastructure to manage their state, meaning that Ansible and Terraform are considered masterless systems.

# Terraform vs. Ansible: 3 Differences

If you use both Terraform and Ansible in your environment, you should know that they have differences, which deﬁne their uses in DevOps. Ansible is for conﬁgurations, while Terraform is for provisioning mutable infrastructure. It uses the HLC syntax, while Ansible uses the common YAML syntax.

The big difference is that Terraform is declarative, which means that code can be dispersed across multiple ﬁles, and code isn’t executed in sequence. The Ansible YAML syntax is procedural, which means that every line of code is executed sequentially. Ansible playbooks are a series of executable tasks used to deﬁne conﬁgurations, which usually needs to be done in order for it to be successful.

Terraform allows for mutable functionality, which means that infrastructure can be changed to run newer applications or hardware. Ansible is immutable, which means that new infrastructure must be deployed if you change conﬁgurations.

# When to Use Terraform

If you have a DevOps team that needs to rapidly deploy infrastructure along with applications, Terraform

will give developers easy access to API endpoints for fast deployments. Developers can connect to a terminal where they can write and test code before they put it into production.

It is mainly used for simple provisioning without many conﬁgurations. It has some conﬁguration functionality during deployment, but it’s not a good choice if you need to automate conﬁgurations on your public cloud hardware. For example, provisioning a virtual machine for use with software could be a good use for Terraform.

# When to Use Ansible

After provisioning hardware, Ansible is a good choice for continual conﬁguration of resources. Ansible is speciﬁc for conﬁgurations, so it’s best for automating cloud resources to work with speciﬁc applications. It can also be used to help other departments as they need to make conﬁguration changes to infrastructure.

For example, let’s say that you provision a virtual machine but need to add it to a load balancer. The conﬁgurations could be automated using Ansible.

# Terraform vs. Ansible: FAQs

## Can you run Ansible from Terraform?

Although Ansible and Terraform are different platforms, you can invoke Ansible from Terraform. This would be done after you provision infrastructure from Terraform and then conﬁgure it using Ansible. You ﬁrst need to create an Ansible playbook and then call Ansible from your Terraform HCL script.

## Can Ansible replace Terraform?

Ansible can be used to deploy some infrastructure, but it can’t completely replace Terraform. It deploys infrastructure, and then Ansible will execute after infrastructure deployment to conﬁgure it. They work well bundled together in a DevOps environment.