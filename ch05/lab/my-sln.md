# Lab Assignment

## Goal

## Tests

✅ Can run app

mweh Can add and retrieve data

Cache persists after deleting pods

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
Solution add a cache volume backed by an `emptyDir`: 43df080e5603df242b46f51bc89f277e678f1dbe

There seems to be sth wrong with the todo app again, since it does not seem to sue the appsettings correctly (it creates a database in the application root instead of the designated location).

## Learnings

Sadly, the exercise with the todo list app fails again, i will not do any more exercises with it.

Applying the manifests from the solution file did not work either, data is not getting saved and/or retrieved.
Like in my solution, the db is in the app root instead of the configured location.
