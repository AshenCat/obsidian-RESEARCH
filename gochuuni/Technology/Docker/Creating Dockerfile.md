| command | Description |
|-----|-----|
| FROM _image_ | the image which needs to be used as base image. Very first command in Dockerfile |
| ADD _host-files_ _container-files_ | Adds files from your host into your image|
| RUN _envVar_ _envValue_ | Sets an environment variable in the image |
| WORKDIR _dir_ | Sets a default working directory. [if we ignore / is the working directory] |
| EXPOSE _port-#_ | Exposes a port for your application |
| ENTRYPOINT _command-to-be-executed_ | Command to be executed once a container is created from this image |
| # | Comments the line |


E.G.

```dockerfile
FROM image
ADD /my/TEST.java /a/b/c/Test.java
RUN apt-get install java
ENV JAVA_HOME=/some/path
WORKDIR /a/b/c
EXPOSE 8050
ENTRYPOINT sleep 5
```

