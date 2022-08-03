## Summary

This is a simple project that's based on the [Cloud Builder Git image Dockerfile](https://github.com/GoogleCloudPlatform/cloud-builders/tree/master/git). In the repo, `oci-image-artifact-registry.yaml` contains a Task `oci-image-artifact-registry`, which uses [Kaniko](https://github.com/GoogleContainerTools/kaniko) and a TaskRun for it, to build the `git` image and upload it to GCR.

## Setup

The Task and TaskRun needs to set up authentication to GCR. The easiest way is to follow the instructions for [setting up Workload Identity](https://github.com/GoogleContainerTools/kaniko#pushing-to-gcr-using-workload-identity) in Kaniko. Notice that Workload Identity only works for Kaniko [specific versions](https://github.com/GoogleContainerTools/kaniko/issues/1805).

Apply Task:
```
kubectl apply -f oci-image-artifact-registry.yaml
```