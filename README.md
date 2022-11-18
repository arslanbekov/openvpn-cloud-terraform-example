# Example usage terraform OpenVPN Cloud provider

This is not official documentation or recommendations for use. Please refer to the provider's official documentation on github or in the registry

- GitHub — [OpenVPN/terraform-provider-openvpn-cloud](https://github.com/OpenVPN/terraform-provider-openvpn-cloud)
- Provider — [registry.terraform.io](https://registry.terraform.io/providers/OpenVPN/openvpn-cloud/latest/docs)

## Configure access

You can use two ways for auth in OpenVPN Cloud.

1. Use ENV variables:

```bash
export OPENVPN_CLOUD_CLIENT_ID=""
export OPENVPN_CLOUD_CLIENT_SECRET=""
```

2. Configure in [provider.tf](https://github.com/arslanbekov/openvpn-cloud-terraform-example/blob/main/provider.tf) file.

## Run

```bash
terraform init

terraform plan
terraform apply
```

## Important notes

Due to rate limits on OpenVPN Cloud side, we have to limit the number of actions that terraform performs in parallel.

Always use `-parallelism=1` with plan and apply commands.

## How to import users

```bash
terraform import 'openvpncloud_user.this["USERNAME"]' USERNAME
```
