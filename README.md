# markoshust/meteor

Standard Dockerfile for deploying bundled Meteor apps.

## Description

This is a simple onbuild Dockerfile for running Meteor 1.3+ with Docker.

## Usage

Just create a new `Dockerfile` in the root of your application, specifying the version of Node you want to use:

```
FROM markoshust/meteor:4.5
```

Then, build your Docker image by running:

```
docker build -t foo/bar:1.0.0 .
```

## Advanced Usage

Place the [.builddeploy](https://github.com/markoshust/docker-meteor/blob/master/.builddeploy) in the root of your Meteor directory, update it's contents where appropriate, make it executable, then run the command:

```
./.builddeploy production 1.0.0
```

This will build a Docker image for the appropriate environment (staging/production) and the appropriate tag (ex. 1.0.0), push it to a Docker registry, then start a container on your production server with your desired configuration.
