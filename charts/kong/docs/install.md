## Install

To install Kong:

```bash
$ helm repo add kong https://charts.konghq.com
$ helm repo update

$ helm install kong/kong --generate-name --set ingressController.installCRDs=false
```

## Uninstall

To uninstall/delete a Helm release `my-release`:

```bash
$ helm delete my-release
```

The command removes all the Kubernetes components associated with the
chart and deletes the release.

> **Tip**: List all releases using `helm list`

## Kong Enterprise prerequisites

If using Kong Enterprise, several additional steps are necessary before
installing the chart:

- Set `enterprise.enabled` to `true` in `values.yaml` file.
- Update values.yaml to use a Kong Enterprise image.
- Satisfy the two prerequsisites for
  [Enterprise License](./configuration.md#kong-enterprise-license) and
  [Enterprise Docker Registry](./configuration.md#kong-enterprise-docker-registry-access).
- (Optional) [set a `password` environment variable](./configuration.md#rbac) to create the
  initial super-admin. Though not required, this is recommended for users that
  wish to use RBAC, as it cannot be done after initial setup.

Once you have these set, it is possible to install Kong Enterprise.

Please read through
[Kong Enterprise considerations](./configuration.md#kong-enterprise-parameters)
to understand all settings that are enterprise specific.

## Example configurations

Several example values.yaml are available in the
[example-values](https://github.com/Kong/charts/blob/main/charts/kong/example-values/)
directory. See the [deployment options guide](./deployment-options.md) for more
information about the options these examples enable.