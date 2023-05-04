# Op1st DevSecOps by #B4mad

This repository will deploy Red Hat OpenShift GitOps, and an app-of-apps.

It implements [Operate First SIG/SRE Infrastructure Services](https://github.com/operate-first/community/issues/251)
and partialy [Hybride Cloud Patterns: Multicluster DevSecOps](https://hybrid-cloud-patterns.io/patterns/devsecops/)

## Directory Structure

All kustomize manifests are located below the `manifests/` directory.

### Resources

Manifests that are generally useful or applicable are located in the `resources/` directory. These are not intended
to be deployed directly, but rather used as a base for other (environment specific) manifests.

### Organizational Unit scoped manifests

These manifests are valid and applicaple to the whole #B4mad organizational unit of Operate First, they should be
deployed to each of our clusters.

### Cluster scoped manifests

These manifests are valid and applicable to a single cluster, they should be deployed to a cluster. They are agnostic
to any organizational unit and implement a specific functionality/configuration that is generally applicable.

### Environment scoped manifests

These manifests are valid and applicable to a single environment, they should be deployed to a cluster and may reference
ou or cluster scoped manifests. They implement a specific functionality/configuration that is specific to a single
environment.

## Usage

To configure a specific environment, run `kustomize build manifests/environments/nostromo | oc apply -f -`
