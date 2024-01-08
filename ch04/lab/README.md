# Lab Assignment

## Goal

Configure a k8s cluster for "adminer", a web application for adminstering databases.

## Tests

We can browse the web app.

We can use the web app.

The app uses the new design (named "price")

## Steps

1. Apply the postgres manifest.
2. Apply the adminer manifest.
3. Find IP address and browse the website.
4. configure the app to use the postgress database
   1. Set env variable `ADMINER_DEFAULT_SERVER` from a secret
5. change ui design
   1. Set env variable `ADMINER_DESIGN`, then ui should look like: 

![ui with price design](./solution/adminer.png)

```bash
kubectl apply -f postgres
kubectl apply -f my_sln
```

Then browse <http://localhost:8082>.

## Learnings

Although k8s has mechanisms for handling secrets, it still depends on external systems and tools to ecurely store secrets at rest (either the filesystem or some other tool).

So: learn some other tools.

It is really nice to be able to delete pods and apply new app manifests; works like a charm. I feel in control, and that a lot is taking care of for me (e.g. networking).

Zsh completion is really convenient; e.g. deleting a pod by name is trivial with tab completion.
