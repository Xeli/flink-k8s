# flink-k8s
Skeleton project to run Flink applications on Kubernetes

## Building the docker images
There are two docker images. [flink-base](/docker/flink-base) and [example-application](/docker/example-application). Because the example-application uses the flink-base image you might need to edit the [Dockerfile](/docker/example-application/Dockerfile) to point to the correct image.


### Kubernetes on Google Cloud Platform example
For instance if you are building for kubernetes on the google cloud you might do something like:


```
docker build /docker/flink-base -t eu.gcr.io/my-google-project/flink-base:1.0
docker push eu.gcr.io/my-google-project/flink-base:1.0
```
In the example-application [Dockerfile](/docker/example-application/Dockerfile) change

```
FROM flink-base:1.0
```

to 

```
FROM eu.gcr.io/my-google-project/flink-base:1.0
```

and run

```
docker build /docker/example-application -t eu.gcr.io/my-google-project/example-application:1.0
docker push eu.gcr.io/my-google-project/example-application:1.0
```
