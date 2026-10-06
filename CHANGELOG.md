CHANGELOG
=========

## 0.3.0 (2026-10-06)

**Rebranded from `eventstorecloud` to `kurrentcloud`** to match the Kurrent Cloud Terraform provider.

- **Service Account authentication**: new optional `clientSecret` (secret) and `identityKitUrl`
  provider config. When both `clientId` and `clientSecret` are set (or `ESC_CLIENT_ID` /
  `ESC_CLIENT_SECRET` via the environment), the provider authenticates with the OAuth2
  client-credentials grant instead of the `token` refresh-token flow.
- Re-pointed the Terraform bridge to `kurrent-io/terraform-provider-kurrentcloud` at the commit released
  as v3.1.0 (was `EventStore/terraform-provider-eventstorecloud` v1.6.0). That release keeps the Go module
  path `…/v2`, so it is required as the pseudo-version `v2.1.2-0.20260729161653-f38d05aa017c`.
- The AWS `gp2` disk type is no longer accepted, because the Kurrent Cloud API rejects it. Use `gp3`, which
  requires `diskIops` and `diskThroughput`. (breaking)
- **New resource:** `ManagedClusterReplicaset` — read-only replica sets attached to a managed cluster.
- Renamed the Pulumi package, resource tokens, namespaces, and SDK packages to `kurrentcloud` /
  `@kurrent/pulumi-kurrentcloud` / `pulumi_kurrentcloud` / `Kurrent.Pulumi.KurrentCloud`. Existing stacks
  migrate without resource replacement via Pulumi aliases — see [MIGRATION.md](./MIGRATION.md). (breaking)
- Moved the repository to `kurrent-io/pulumi-kurrentcloud` (renamed from `pulumi-eventstorecloud`; the old
  URLs redirect). The Go SDK module is now `github.com/kurrent-io/pulumi-kurrentcloud/sdk`, imported as
  `github.com/kurrent-io/pulumi-kurrentcloud/sdk/go/kurrentcloud`. (breaking for Go)
- The Go SDK is now tagged `sdk/vX.Y.Z` on every release, so `go get` resolves each version. The old
  provider's Go SDK stopped at `sdk/v0.2.15`.
- Release artifacts publish without stored keys: NuGet, npm and PyPI through trusted publishing.
- The .NET package and namespace are `Kurrent.Pulumi.KurrentCloud`. Pulumi has reserved the `Pulumi.`
  prefix on nuget.org, so a new `Pulumi.KurrentCloud` package cannot be created. (breaking for .NET)
- The Python SDK reads its version with `importlib.metadata` instead of `pkg_resources`, which current
  `setuptools` no longer ships; importing the SDK failed in a fresh environment.
- Inherited the upstream in-place `projectionLevel` update behavior (no longer forces cluster replacement).

## 0.1.2 (Initial release)

- First release using the Terraform bridge and ESC Terraform provider
- SDK packages are on GitHub package registry, check `README` for instructions

## 0.2.0

- Update to TF provider 1.5.9

## 0.3.0 (never tagged; `eventstorecloud` releases continued as 0.2.x)

- Renamed the namespace to `EventStoreCloud` (breaking)

---
