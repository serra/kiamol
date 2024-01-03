# Lab Assignment

## Goal

Deploy services for updated version of numbers app.

## Tests

```bash
kubectl apply -f deployments.yaml
kubectl get pods
```

> There are two versions of the web app

[services.yaml](./solution/services.yaml) defines a ClusterIP service for the API and a LoadBalancer service for the web app. The selector for the web service uses two labels to ensure only the v2 pod is included.

```
kubectl apply -f solution/services.yaml
```

> http://localhost:8088

![](./solution/numbers-web-v2.png)


## Steps

1. deploy the applications from the application manifest
2. inspect what pods are running
   1. what services are already running?
      1. only the k8s clusterip
   2. what pods are already running?
      1. three pods (api, web, web-v2)
   3. if needed configure services in a separate file
      1. configure a local service for the api
      2. configure a load balancer, first select web v1

## Learnings

When reapplying a manifest, k8s knows what to patch or create.

Selectors in services differ from pod templates in deployment; the `matchLabel:` is not needed in services.
