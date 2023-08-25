# UDS Capability Gitlab

## How to upgrade this capability

This package is pulling in the [bigbang gitlab chart](https://repo1.dso.mil/big-bang/product/packages/gitlab)

The [gitlab-flux-values.yaml](../gitlab-flux-values.yaml) file contains values used when creating the flux resources for this capability. This includes the version of the chart and the base values used for this capability.

To upgrade
1) Point `application.ref.tag` to the updated version of the chart.
1) Update any base values if necessary.
1) Update the `gitlab` component in the [zarf.yaml](../zarf.yaml) file to pull in the correct images needed for the update version of the chart.

## How to test this capability

With docker running and while connected to an aws account, at the root of this repository, you can run `make test`. This will provision an ec2 instance, build and deploy all dependencies and packages, and run an e2e test to insure the capability is deploying successfully, available and ready.

You can also follow the bread crumbs of the Makefile to manually create the cluster as well as build and deploy all the necessary packages.