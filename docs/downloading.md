# Factory-cli: Downloading #

## Background ##

As mentioned,, in order to address the bandwidth limitations, a factory pre-staging solution is required to eliminate the download of artifacts at the remote site.The factory-precaching-cli tool facilitates the pre-staging of servers before they are shipped to the site for later ZTP provisioning. Remember that the idea is to focus on those servers where only one disk is available and no external disk drive is possible to be attached.

This downloading stage managed both the pull of the OCP release images, and if required, it can also manage the download of the operators included in the distributed unit (DU) profile for telco 5G RAN sites.

> :warning: Notice that the list of operators can vary depending on the OCP version we are about to install. For instance, in OCP 4.12 the DU profile adds: AMQ, LVM and the baremetal-event operators compared to 4.11.

## Pre-requisites

* The [partitioning stage](../partitioning.md) must be already executed successfully before moving to the downloading stage where all artifacts are stored on the local partition.
* Currently the bare metal server needs to be connected to the Internet to create the dependency of images that need to be pulled down.
* A valid pull-secret to the registries involved in the downloading process of the container images is required. At least the pull secret that authenticates against the official Red Hat registries is needed. It can be obtained from the [Red Hat's console UI](https://console.redhat.com/openshift/downloads#tool-pull-secret)
* Enough space in the partition where the artifacts are going to be stored is required. See [Partitioning pre-requisites section](../partitioning/#pre-requisites) 


 ## Downloading the artifacts

In this stage we can split the tasks up to downloading the OCP release container images and the day-2 operators, specifically the telco DU profile approved operators.

### OCP release 




