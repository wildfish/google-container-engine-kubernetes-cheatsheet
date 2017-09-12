# Google Container Engine (GKE) and Kubernetes (K8s) Cheatsheet

## Kubernetes

Show namespaces:

    kubectl get ns
    
Show all events and watch for updates:

    kubectl get events -w

Show pods and watch for updates:

    kubectl get pod -w

Run a bash shell on a pod:

    kubectl exec <pod-id> -it bash

Patch a running deployment with a new container image:

    kubectl patch deployment <deployment-name> -p'{"spec":{"template":{"spec":{"containers":[{"name":"<container-name>","image":"<image-name>"}]}}}}'

Copy a file from a running pod:

    kubectl cp <namespace>/<pod-id>:<pod-file-path> <local-file-path>

## Google Cloud

Authenticate with application default credentials:

    gcloud auth application-default login

Set project:

    gcloud config set project <project>

Set compute zone:

    gcloud config set compute/zone <zone>

Get credentials for a running cluster:

    gcloud container clusters get-credentials <cluster-name>

Create a disk:

    gcloud compute disks create <disk-name> --size 200GB
