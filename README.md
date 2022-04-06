<!-- This file was automatically generated by the `geine`. Make all changes to `README.yaml` and run `make readme` to rebuild this file. -->

<p align="center"> <img src="https://user-images.githubusercontent.com/50652676/62349836-882fef80-b51e-11e9-99e3-7b974309c7e3.png" width="100" height="100"></p>


<h1 align="center">
    Terraform AWS VPN
</h1>

<p align="center" style="font-size: 1.2rem;"> 
    Terraform module is used to create VPN resource on AWS for network connectivity..
     </p>

<p align="center">

<a href="https://www.terraform.io">
  <img src="https://img.shields.io/badge/Terraform-v1.1.7-green" alt="Terraform">
</a>
<a href="LICENSE.md">
  <img src="https://img.shields.io/badge/License-APACHE-blue.svg" alt="Licence">
</a>
<a href="https://github.com/clouddrove/terraform-aws-vpn/actions/workflows/tfsec.yml">
  <img src="https://github.com/clouddrove/terraform-aws-vpn/actions/workflows/tfsec.yml/badge.svg" alt="tfsec">
</a>
<a href="https://github.com/clouddrove/terraform-aws-vpn/actions/workflows/terraform.yml">
  <img src="https://github.com/clouddrove/terraform-aws-vpn/actions/workflows/terraform.yml/badge.svg" alt="static-checks">
</a>


</p>
<p align="center">

<a href='https://facebook.com/sharer/sharer.php?u=https://github.com/clouddrove/terraform-aws-vpn'>
  <img title="Share on Facebook" src="https://user-images.githubusercontent.com/50652676/62817743-4f64cb80-bb59-11e9-90c7-b057252ded50.png" />
</a>
<a href='https://www.linkedin.com/shareArticle?mini=true&title=Terraform+AWS+VPN&url=https://github.com/clouddrove/terraform-aws-vpn'>
  <img title="Share on LinkedIn" src="https://user-images.githubusercontent.com/50652676/62817742-4e339e80-bb59-11e9-87b9-a1f68cae1049.png" />
</a>
<a href='https://twitter.com/intent/tweet/?text=Terraform+AWS+VPN&url=https://github.com/clouddrove/terraform-aws-vpn'>
  <img title="Share on Twitter" src="https://user-images.githubusercontent.com/50652676/62817740-4c69db00-bb59-11e9-8a79-3580fbbf6d5c.png" />
</a>

</p>
<hr>


We eat, drink, sleep and most importantly love **DevOps**. We are working towards strategies for standardizing architecture while ensuring security for the infrastructure. We are strong believer of the philosophy <b>Bigger problems are always solved by breaking them into smaller manageable problems</b>. Resonating with microservices architecture, it is considered best-practice to run database, cluster, storage in smaller <b>connected yet manageable pieces</b> within the infrastructure. 

This module is basically combination of [Terraform open source](https://www.terraform.io/) and includes automatation tests and examples. It also helps to create and improve your infrastructure with minimalistic code instead of maintaining the whole infrastructure code yourself.

We have [*fifty plus terraform modules*][terraform_modules]. A few of them are comepleted and are available for open source usage while a few others are in progress.




## Prerequisites

This module has a few dependencies: 

- [Terraform 1.x.x](https://learn.hashicorp.com/terraform/getting-started/install.html)
- [Go](https://golang.org/doc/install)
- [github.com/stretchr/testify/assert](https://github.com/stretchr/testify)
- [github.com/gruntwork-io/terratest/modules/terraform](https://github.com/gruntwork-io/terratest)







## Examples


**IMPORTANT:** Since the `master` branch used in `source` varies based on new modifications, we suggest that you use the release versions [here](https://github.com/clouddrove/terraform-aws-vpn/releases).


### Simple Example
Here is an example of how you can use this module in your inventory structure:
  ```hcl
  module "vpn" {
      source              = "clouddrove/vpn/aws"
      version             = "0.15.0"
      name                = "vpn"
      environment         = "test"
      label_order         = ["environment", "name"]
      vpc_id              = "vpc-xxxxxxxxxx"
      customer_ip_address = "115.160.246.74"
    }
  ```






## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| application | Application (e.g. `cd` or `clouddrove`). | `string` | `""` | no |
| attributes | Additional attributes (e.g. `1`). | `list(any)` | `[]` | no |
| certificate\_arn | certificate\_arn (e.g. ''). | `string` | `""` | no |
| customer\_ip\_address | The IP of the Customer Gateway. | `string` | n/a | yes |
| delimiter | Delimiter to be used between `organization`, `environment`, `name` and `attributes`. | `string` | `"-"` | no |
| enable\_vpn\_connection | Set to false to prevent the creation of a VPN Connection. | `bool` | `true` | no |
| enable\_vpn\_gateway\_attachment | Set to false to prevent attachment of the vGW to the VPC. | `bool` | `true` | no |
| environment | Environment (e.g. `prod`, `dev`, `staging`). | `string` | `""` | no |
| label\_order | Label order, e.g. `name`,`application`. | `list(any)` | `[]` | no |
| local\_ipv4\_network\_cidr | n/a | `string` | `"0.0.0.0/0"` | no |
| managedby | ManagedBy, eg 'CloudDrove' or 'AnmolNagpal'. | `string` | `"anmol@clouddrove.com"` | no |
| name | Name  (e.g. `app` or `cluster`). | `string` | `""` | no |
| remote\_ipv4\_network\_cidr | n/a | `string` | `"0.0.0.0/0"` | no |
| tags | Additional tags (e.g. map(`BusinessUnit`,`XYZ`). | `map(any)` | `{}` | no |
| tunnel1\_inside\_cidr | The CIDR block of the inside IP addresses for the first VPN tunnel. | `string` | `""` | no |
| tunnel1\_preshared\_key | The preshared key of the first VPN tunnel. | `string` | `""` | no |
| tunnel2\_inside\_cidr | The CIDR block of the inside IP addresses for the second VPN tunnel. | `string` | `""` | no |
| tunnel2\_preshared\_key | The preshared key of the second VPN tunnel. | `string` | `""` | no |
| vpc\_id | The id of the VPC where the VPN Gateway lives. | `string` | n/a | yes |
| vpc\_subnet\_route\_table\_count | The number of subnet route table ids being passed in via `vpc_subnet_route_table_ids`. | `string` | `0` | no |
| vpc\_subnet\_route\_table\_ids | The ids of the VPC subnets for which routes from the VPN Gateway will be propagated. | `list(string)` | `[]` | no |
| vpn\_connection\_static\_routes\_destinations | List of CIDRs to be used as destination for static routes (used with `vpn_connection_static_routes_only = true`). Routes to destinations set here will be propagated to the routing tables of the subnets defined in `vpc_subnet_route_table_ids`. | `list(string)` | `[]` | no |
| vpn\_connection\_static\_routes\_only | Set to true for the enabled VPN connection to use static routes exclusively (only if `enable_vpn_connection = true`). Static routes must be used for devices that don't support BGP. | `bool` | `false` | no |

## Outputs

| Name | Description |
|------|-------------|
| customer\_gateway\_id | The ID of the VPN Connection Route. |
| gateway\_attachment\_id | The ID of the Gateway Attachment. |
| tags | A mapping of tags to assign to the resource. |
| vpn\_connection\_id | The ID of the VPN Connection. |
| vpn\_gateway\_id | The ID of the VPN gateway. |




## Testing
In this module testing is performed with [terratest](https://github.com/gruntwork-io/terratest) and it creates a small piece of infrastructure, matches the output like ARN, ID and Tags name etc and destroy infrastructure in your AWS account. This testing is written in GO, so you need a [GO environment](https://golang.org/doc/install) in your system. 

You need to run the following command in the testing folder:
```hcl
  go test -run Test
```



## Feedback 
If you come accross a bug or have any feedback, please log it in our [issue tracker](https://github.com/clouddrove/terraform-aws-vpn/issues), or feel free to drop us an email at [hello@clouddrove.com](mailto:hello@clouddrove.com).

If you have found it worth your time, go ahead and give us a ★ on [our GitHub](https://github.com/clouddrove/terraform-aws-vpn)!

## About us

At [CloudDrove][website], we offer expert guidance, implementation support and services to help organisations accelerate their journey to the cloud. Our services include docker and container orchestration, cloud migration and adoption, infrastructure automation, application modernisation and remediation, and performance engineering.

<p align="center">We are <b> The Cloud Experts!</b></p>
<hr />
<p align="center">We ❤️  <a href="https://github.com/clouddrove">Open Source</a> and you can check out <a href="https://github.com/clouddrove">our other modules</a> to get help with your new Cloud ideas.</p>

  [website]: https://clouddrove.com
  [github]: https://github.com/clouddrove
  [linkedin]: https://cpco.io/linkedin
  [twitter]: https://twitter.com/clouddrove/
  [email]: https://clouddrove.com/contact-us.html
  [terraform_modules]: https://github.com/clouddrove?utf8=%E2%9C%93&q=terraform-&type=&language=
