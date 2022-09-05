# Doge Hello World

Example app using the [Doge](https://github.com/martibosch/cookiecutter-doge) :dog2: workflow for continuous deployment to Digital Ocean.

## Requirements

### Software

* GNU Make
* terraform
* 

### Accounts

* A DigitalOcean account. You can sign up using [my referral link](https://m.do.co/c/fcde1e9e1f62) to get $100 in credit.
* A GitHub account.
* A Terraform Cloud account and a Terraform Cloud organization. With an active account, you can create an organization by navigating to [app.terraform.io/app/organizations/new](https://app.terraform.io/app/organizations/new). You can also use an existing organization. This workflow is compatible with [the free plan](https://www.terraform.io/cloud-docs/overview).

## Steps

### 1. Create access tokens

The Doge :dog2: workflow requires three access tokens, which must be set as terraform variables in the `terraform/deploy/meta/vars.tfvars` file (**note** that to avoid disclosing sensitive information, this file is kept out of version control):

* **DigitalOcean**: navigate to [cloud.digitalocean.com/account/api/token/new](https://cloud.digitalocean.com/account/api/tokens/new) (you must be authenticated), choose a name and an expiration, click on "Generate Token" and copy the generated token as the value of the `do_token` variable.
* **GitHub**: navigate to [github.com/settings/tokens/new](https://github.com/settings/tokens/new) (you must be authenticated), choose a name, an expiration and select at least the `repo` and `workflow` permissions. Click on "Generate token" and copy the generated token as the value of the `gh_token` variable.
* **Terraform Cloud**: navigate to [app.terraform.io/app/settings/tokens](https://app.terraform.io/app/settings/tokens) and click on "Create an API token", provide a description, click on "Create API token" and copy the generated token as the value of the `tf_api_token` variable.

### 2. Initial infrastructure provisioning



```
make init-meta
make plan-meta
make apply-meta
```

Navigate to [app.terraform.io/app/exaf-epfl/workspaces](https://app.terraform.io/app/exaf-epfl/workspaces)



[![Built with Doge](https://img.shields.io/badge/built%20with-Doge-orange)](https://github.com/martibosch/cookiecutter-doge).
