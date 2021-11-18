---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "awsutils_guardduty_organization_settings Resource - terraform-provider-awsutils"
subcategory: ""
description: |-
  Enables a list of accounts as GuardDuty member accounts in an existing AWS Organization.
  Designating an account as the GuardDuty Administrator account in an AWS Organization can optionally enable all
  newly created accounts and accounts that join the organization after the setting is enabled, however it does not
  enable existing accounts. Use this resource to enable a list of existing accounts
---

# Resource `awsutils_guardduty_organization_settings`

Enables a list of accounts as GuardDuty member accounts in an existing AWS Organization.

Designating an account as the GuardDuty Administrator account in an AWS Organization can optionally enable all 
newly created accounts and accounts that join the organization after the setting is enabled, however it does not 
enable existing accounts. Use this resource to enable a list of existing accounts

## Example Usage

```terraform
terraform {
  required_providers {
    awsutils = {
      source = "cloudposse/awsutils"
      # For local development,
      # install the provider on local computer by running `make install` from the root of the repo, and uncomment the 
      # version below
      # version = "9999.99.99"
    }
  }
}

provider "awsutils" {
  region = "us-east-1"
}

resource "awsutils_guardduty_organization_settings" "default" {
  member_accounts = ["111111111111", "22222222222"]
  detector_id     = "42bd3eab69b96663418094bb59397d1f"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- **detector_id** (String)
- **member_accounts** (Set of String) A list of AWS Organization member accounts to associate with the GuardDuty Administrator account.

### Read-only

- **id** (String) The ID of this resource.

