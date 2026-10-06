# Pulumi provider for Kurrent Cloud

The Kurrent Cloud provider allows you to manage resources in [Kurrent Cloud](https://www.kurrent.io/kurrent-cloud).

## Installation

This package is available in many languages in the standard packaging formats.

### Configure the provider

The following configuration points are available for the `kurrentcloud` provider:

- `kurrentcloud:organizationId` - the organization ID for an existing organization in Kurrent Cloud
- `kurrentcloud:clientId` / `kurrentcloud:clientSecret` - Service Account credentials (recommended for automation); when both are set they take priority over `token`
- `kurrentcloud:token` - a valid refresh token for an Kurrent Cloud account with admin access to the organization

### Install SDK


Add the NuGet package `Kurrent.Pulumi.KurrentCloud` to your Pulumi project, which uses the .NET Pulumi SDK.
### Get the plugin

For projects that use .NET and Go Pulumi SDK you have to install the provider before trying to update the stack.

Use the following command to add the plugin to your environment:

```
pulumi plugin install resource kurrentcloud [version] \
  --server https://github.com/kurrent-io/pulumi-kurrentcloud/releases/download/[version]
```

Example:

```
pulumi plugin install resource kurrentcloud v0.3.0 \
  --server https://github.com/kurrent-io/pulumi-kurrentcloud/releases/download/v0.3.0
```
