# nuxtjs-deployer
A docker image used for deploying nuxt js applications with deployer and bitbucket pipelines.

## Build, tag and push to docker hub

```
docker login --username your-docker-username
#username: your-docker-username
#password: your-docker-password

git clone git@github.com:iuliansafta/nuxtjs-deployer.git

cd nuxtjs-deployer

docker build -t your-docker-username/nuxtjs-deployer:tagname .
docker push your-docker-username/nuxtjs-deployer:tagname
```

## Use it in bitbucket-pipelines.yml

```
pipelines:
  default:
    - step:
        name: Deploy to STAGING
        image: your-docker-username/nuxtjs-deployer:tagname
        script:
          - dep deploy staging
```