CHANGELOG
=========

## 0.3.0 (unreleased)

**Rebranded from `eventstorecloud` to `kurrentcloud`** to match the Kurrent Cloud Terraform provider.

- Re-pointed the Terraform bridge to `kurrent-io/terraform-provider-kurrentcloud` v2.1.1 (was
  `EventStore/terraform-provider-eventstorecloud` v1.6.0).
- **New resource:** `ManagedClusterReplicaset` — read-only replica sets attached to a managed cluster.
- Renamed the Pulumi package, resource tokens, namespaces, and SDK packages to `kurrentcloud` /
  `@kurrent/pulumi-kurrentcloud` / `pulumi_kurrentcloud` / `Pulumi.KurrentCloud`. Existing stacks
  migrate without resource replacement via Pulumi aliases — see [MIGRATION.md](./MIGRATION.md). (breaking)
- Moved the repository to `kurrent-io/pulumi-kurrentcloud` (renamed from `pulumi-eventstorecloud`; the old
  URLs redirect). The Go SDK module is now `github.com/kurrent-io/pulumi-kurrentcloud/sdk`, imported as
  `github.com/kurrent-io/pulumi-kurrentcloud/sdk/go/kurrentcloud`. (breaking for Go)
- The Go SDK is now tagged `sdk/vX.Y.Z` on every release, so `go get` resolves each version. The old
  provider's Go SDK stopped at `sdk/v0.2.15`.
- Release artifacts publish without stored keys: NuGet, npm and PyPI through trusted publishing.
- Inherited the upstream in-place `projectionLevel` update behavior (no longer forces cluster replacement).

## 0.1.2 (Initial release)

- First release using the Terraform bridge and ESC Terraform provider
- SDK packages are on GitHub package registry, check `README` for instructions

## 0.2.0

- Update to TF provider 1.5.9

## 0.3.0 (never tagged; `eventstorecloud` releases continued as 0.2.x)

- Renamed the namespace to `EventStoreCloud` (breaking)

---
