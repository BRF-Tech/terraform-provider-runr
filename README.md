# terraform-provider-runr

The Terraform (and OpenTofu) provider for [RunR](https://runr.sh), the open-source serverless
platform on Kubernetes and Knative. It manages projects with their triggers, network, deploy
strategy and global placement, environments, environment variables and secret store references,
custom domains, deployments, bindings, private connections, topics, runtime plugins, durable
workflows, model services, hosted MCP servers, the API product of the gateways, secret stores, cost
limits, access control and branding.

runr.sh serves the provider registry protocol, so `terraform init` installs the provider from
there and checks it against the release's `SHA256SUMS`, signed with the RunR release key (key ID
`2588846B241BC095`):

```hcl
terraform {
  required_providers {
    runr = {
      source  = "runr.sh/brf-tech/runr"
      version = "~> 0.6"
    }
  }
}

provider "runr" {
  api_url = "https://runr.example.com"
  token   = var.runr_token
}
```

- Guide with examples: [runr.sh/docs/terraform](https://runr.sh/docs/terraform/)
- Reference for every resource and data source: [docs/](docs/index.md), also at
  [runr.sh/docs/terraform/reference](https://runr.sh/docs/terraform/reference/)
- Downloads and the signing key: [runr.sh/dl](https://runr.sh/dl/)

This repository is the release mirror of `terraform-provider-runr/` in RunR's repository, where
the provider is developed. Each release here carries the same signed archives that runr.sh
serves.

## Build

```sh
make build   # ./terraform-provider-runr
make test    # tests against a fake RunR API (needs the terraform CLI, 1.11 or later)
make docs    # regenerate docs/ with tfplugindocs
```

## License

[MIT](LICENSE)
