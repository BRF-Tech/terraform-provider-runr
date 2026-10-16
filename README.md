# terraform-provider-runr

The Terraform (and OpenTofu) provider for [RunR](https://github.com/brf-tech/runr), the
open-source serverless platform on Kubernetes and Knative. It manages projects, environment
variables, custom domains, deployments, bindings, runtime plugins, workflow triggers, model
services, hosted MCP servers, access control and branding.

```hcl
terraform {
  required_providers {
    runr = {
      source  = "brf-tech/runr"
      version = "~> 0.5"
    }
  }
}

provider "runr" {
  api_url = "https://runr.example.com"
  token   = var.runr_token
}
```

- Guide with examples: [docs/terraform.md](https://github.com/brf-tech/runr/blob/main/docs/terraform.md) in brf-tech/runr
- Reference for every resource and data source: [docs/](docs/index.md), also on the Terraform Registry

This repository is the release mirror of `terraform-provider-runr/` in
[brf-tech/runr](https://github.com/brf-tech/runr), where the provider is developed. Please open
issues and pull requests there. Each release here carries the signed archives that the
Terraform Registry installs.

## Build

```sh
make build   # ./terraform-provider-runr
make test    # tests against a fake RunR API (needs the terraform CLI, 1.11 or later)
make docs    # regenerate docs/ with tfplugindocs
```

## License

[MIT](LICENSE)
