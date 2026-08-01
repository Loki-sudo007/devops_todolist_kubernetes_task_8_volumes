# Instructions for testing the application

## Checking that the application is up and running

First, let's check if the pods are running and ready:
```bash
kubectl get pods -n todoapp
```

Check if Persistent Volumes have been created:
```bash
kubectl get pv
```
Check if Persistent Volumes Claim have been created:
```bash
kubectl get pvc
```

Open a browser and check if the application is working at this address http://localhost:8080


## Check if the ConfigMap and Secret data are mounted as files in the correct location

First, you need to look at the pod names:
```bash
kubectl get pods -n todoapp
```

Copy the name of the first pod and run the command:
```bash
kubectl exec -it <Pod-name> -n todoapp -- sh
```

Inside the pod, check if there are directories secrets and configs:
```bash
ls
```

Check what is in these directories:
```bash
ls /app/configs
```

```bash
ls /app/secrets
```


