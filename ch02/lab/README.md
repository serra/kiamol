# Lab Assignment

## Goal

Write an application manifest for a deployment that runs a pod hosting a `kiamol/ch02-whoami` container.

Verify that the web app running in the container returns the hostname of the container. 

## Tests

```bash
kubectl apply -f my_deployment.yaml
kubectl port-forward deploy/whoami 8080:80
curl http://localhost:8080
```

✅ Expected output:

> "I'm whoami-1-549786dc89-dps2x running on Linux 6.5.11-linuxkit #1 SMP PREEMPT Wed Dec  6 17:08:31 UTC 2023"

```bash
kubectl get pods -o custom-columns=NAME:metadata.name
```

> whoami-1-549786dc89-dps2x

```bash
kubectl exec deploy/whoami-1 -- sh -c 'hostname'
```

> whoami-1-549786dc89-dps2x

✅ These two names should be the same.

## Steps

1. copy a deployment file from an earlier exercise, rename to my_deployment.yaml
2. read pod.yaml to find pod specifications
3. add those to my_deployment.yaml
4. run tests

## Learnings

Exercise was pretty simple. I do have to brush up my terminal skills again.
It is powerful to use the terminal but at the same time
I could use some sort of GUI to get a graphical overview.
In the solution, an explicit version is used for the deployment and the pod,
I did not do that.