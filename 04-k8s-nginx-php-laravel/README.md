# Laravel as a service in Kubernetes + Nginx

Run this command to install Laravel inside the current directory:

```
docker run --rm -it -v $PWD/code:/app/code composer create-project laravel/laravel code --prefer-dist
```

Add minikube context:

```
eval $(minikube docker-env)
```

Then build the image:

```
docker build . -t my-laravel-app:1.0.0
```

And apply kubernetes configurations and deployments:

```
kubectl apply -f .
```

And get url from minikube to access the app:

```
minikube service nginx-service --url
```

Now you should see the home page of Laravel.

With two replica of nginx service, if we stop one off the services, the other one is up and seving properly and we have a high availble service. 

```
nginx -s stop
```