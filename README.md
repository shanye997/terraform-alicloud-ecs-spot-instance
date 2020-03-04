Alibaba Cloud ECS Spot Instance Terraform Module
terraform-alicloud-ecs-spot-instance
=====================================================================

English | [简体中文](https://github.com/terraform-alicloud-modules/terraform-alicloud-ecs-spot-instance/blob/master/README-CN.md)

Terraform module for creating Spot instance(s) on Alibaba Cloud.

These types of resources are supported:

* [ECS Instance](https://www.terraform.io/docs/providers/alicloud/r/instance.html)

## Terraform versions

The Module requires Terraform 0.12 and Terraform Provider AliCloud 1.56.0+.

## Usage

```hcl
module "ecs_spot_instance" {
  source                      = "terraform-alicloud-modules/ecs-spot-instance/alicloud"
  profile                     = "Your-Profile-Name"
  region                      = "cn-beijing"
  instance_type_family        = "ecs.g6"
  vswitch_id                  = "vsw-fhuqie"
  security_group_ids          = ["sg-12345678"]
  associate_public_ip_address = true
  internet_max_bandwidth_out  = 10
  
  #######################
  #spot strategy setting#
  #######################
  spot_strategy               = "SpotWithPriceLimit"
  spot_price_limit            = 0.5
}

```

## Examples

* [Basic example](https://github.com/terraform-alicloud-modules/terraform-alicloud-ecs-spot-instance/tree/master/examples/basic-example)

## Notes

* This module using AccessKey and SecretKey are from `profile` and `shared_credentials_file`.
If you have not set them yet, please install [aliyun-cli](https://github.com/aliyun/aliyun-cli#installation) and configure it.

Submit Issues
-------------
If you have any problems when using this module, please opening a [provider issue](https://github.com/terraform-providers/terraform-provider-alicloud/issues/new) and let us know.

**Note:** There does not recommend to open an issue on this repo.

Authors
-------
Created and maintained by Wang li(@Lexsss, 13718193219@163.com) and He Guimin(@xiaozhu36, heguimin36@163.com)

License
----
Apache 2 Licensed. See LICENSE for full details.

Reference
---------
* [Terraform-Provider-Alicloud Github](https://github.com/terraform-providers/terraform-provider-alicloud)
* [Terraform-Provider-Alicloud Release](https://releases.hashicorp.com/terraform-provider-alicloud/)
* [Terraform-Provider-Alicloud Docs](https://www.terraform.io/docs/providers/alicloud/index.html)
