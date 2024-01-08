# Lab Assignment

## Goal

## Tests

Can run app

Can add and retrieve data

Data persists after deleting pods



## Steps

Start the cluster

    kubectl apply -f ./todo-list

Find url

    http://localhost:8082

Configure storage for proxy cache files and database. Check pod spec and log entries.

    ➜  lab git:(master) ✗ kubectl logs -p todo-proxy-lab-579d7b9d5d-jmm7z
    2024/01/08 13:34:02 [emerg] 1#1: mkdir() "/data/nginx/cache" failed (2: No such file or directory)
    nginx: [emerg] mkdir() "/data/nginx/cache" failed (2: No such file or directory)

On the proxy pod, the directory `/data/nginx/cache` is missing.



## Learnings