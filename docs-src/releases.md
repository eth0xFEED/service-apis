# Releases

Although Service APIs are an official Kubernetes project, and represent official
APIs, these APIs will not be installed by default on Kubernetes clusters at this
time. This project will use Custom Resource Definitions (CRDs) to represent the
new API types that Service APIs include.

Similar to other Kubernetes APIs, these will go through a formal Kubernetes
Enhancement Proposal (KEP) review. Unlike other Kubernetes APIs, Service API
releases will be independent from Kubernetes releases initially.

Service API releases will include four components:

* Custom Resource Definitions to define the API.
* Go client libraries.
* Validation webhooks to implement cross field validations.
* Conversion webhooks to convert resources between API versions.

## Versioning

Versioning will be completely separate from the Kubernetes release process, but
similar methodology will be used. Service API versions will use the [same
version level requirements as other Kubernetes
features](https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api_changes.md#alpha-beta-and-stable-versions).

## Installation

This project will be responsible for providing straightforward and reliable ways
to install releases of Service APIs.

## Other Official Custom Resources

This is a relatively new concept, and there is only one previous example of
official custom resources being used:
[VolumeSnapshots](https://kubernetes.io/blog/2018/10/09/introducing-volume-snapshot-alpha-for-kubernetes/).
Although VolumeSnapshot CRDs can be installed directly by CSI drivers that
support them, Service APIs must support multiple controllers per cluster, so the
CRDs will live in and be installed from this repo.
