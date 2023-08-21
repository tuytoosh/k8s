# Laravel as a service in Kubernetes + Nginx

Run this command to install Laravel inside the current directory:

```
docker run --rm -it -v $PWD/code:/app/code composer create-project laravel/laravel code --prefer-dist
```
