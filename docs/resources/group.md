---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "chainguard_group Resource - terraform-provider-chainguard"
subcategory: ""
description: |-
  IAM Group on the Chainguard platform.
---

# chainguard_group (Resource)

IAM Group on the Chainguard platform.

## Example Usage

```terraform
# Example managed root group.
resource "chainguard_group" "example" {
  name        = "example-root"
  description = "My example root group."
}

# Example managed sub-group.
resource "chainguard_group" "example_sub" {
  name        = "example-sub-group"
  description = "My example sub group."
  parent_id   = chainguard_group.example.id
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `name` (String) Name of this IAM group.

### Optional

- `description` (String) Description of this IAM group.
- `parent_id` (String) Parent IAM group of this group. If not set, this group is assumed to be a root group.
- `verified` (Boolean) Whether the organization has been verified by a Chainguardian. Only applicable to root groups.
- `verified_protection` (Boolean) Prevent the group from being unverified through Terraform. Null is treated as true.

### Read-Only

- `id` (String) The exact UIDP of this IAM group.

## Import

Import is supported using the following syntax:

The [`terraform import` command](https://developer.hashicorp.com/terraform/cli/commands/import) can be used, for example:

```shell
# Group can be imported by specifying the exact UIDP of the group
terraform import chainguard_group.example fb694596eb1678321f94eec283e1e0be690f655c/ae3a1bdc96e6f1a4
```
