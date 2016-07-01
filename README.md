# coldrye-debian-jenkins

[![coldrye/debian-jenkins](http://dockeri.co/image/coldrye/debian-jenkins)](https://hub.docker.com/r/coldrye/debian-jenkins/)


## Description

This packages Jenkins CI 2 using the most release from mirrors.jenkins-ci.org/war based on coldrye/debian-jetty.


## Image Releases

Images are released for the following debian releases.

- jessie
- testing (stretch)

See https://hub.docker.com/r/coldrye/debian-docker-jenkins/tags/ for a complete list.


## Usage

While you can use this as it is and have a working Jenkins CI 2 installation, one might consider that
existing data needs to be stored on a persistent volume.

The persistent volume must be mounted inside the container on ``/var/storages/jenkins`` and must have the following layout

```
cacerts  // optional, copy over the keystore from /usr/lib/jvm/.../jre/lib/security/cacerts
```

After which the container can be created using

```
docker create -P -v ./jenkins:/var/storages/jenkins coldrye/debian-jenkins:2-10-<jessie|testing>-latest
```

