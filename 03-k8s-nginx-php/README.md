# Run Kubernetes with PHP-FPM and Nginx 

Steps to follow:

Build the php app:
```
docker build ./code -t my-php-app:1.0.0
```

Apply all yaml files:
```
kubectl apply -f .
```

And get url from minikube to access the app:
```
minikube service nginx-service --url
```

You should see PHP8's info page.