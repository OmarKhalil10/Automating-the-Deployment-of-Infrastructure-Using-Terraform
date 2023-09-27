# Automating the Deployment of Infrastructure Using Terraform

## Objectives
In this lab, you learn how to perform the following tasks:

* Create a configuration for an auto mode network
* Create a configuration for a firewall rule
* Create a module for VM instances
* Create and deploy a configuration
* Verify the deployment of a configuration

## Set up Terraform and Cloud Shell

```
cd tfinfra
```

```
terraform --version
```

## Create mynetwork and its resources

1. To rewrite the Terraform configuration files to a canonical format and style, run the following command:

```
terraform fmt
```

The output should look like this:

```
mynetwork.tf
```

2. To initialize Terraform, run the following command:

```
terraform init
```

3. To create an execution plan, run the following command:

```
terraform plan
```

```
Plan: 4 to add, 0 to change, 0 to destroy.
```

Terraform determined that the following 4 resources need to be added:


Name	                           | Description
-----------------------------------|----------
 mynetwork	                       | VPC network
 mynetwork-allow-http-ssh-rdp-icmp | Firewall rule to allow HTTP, SSH, RDP and ICMP
 mynet-us-vm	                   | VM instance in Zone [europe-west1-d]
 mynet-eu-vm                       | VM instance in "europe-west1-d"

4. To apply the desired changes, run the following command:

```
terraform apply
```

5. To confirm the planned actions, type:

```
yes
```

The output should look like this:

```
Apply complete! Resources: 4 added, 0 changed, 0 destroyed.
```