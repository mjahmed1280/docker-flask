# python-flask-docker
Basic Python Flask app in Docker which prints the hostname and IP of the container

### Build application
Build the Docker image manually by cloning the Git repo.
```
$ git clone https://github.com/mjahmed1280/docker-flask.git
$ docker build -t ahmed/python-flask-docker .
```

### Run the container
Create a container from the image.
```
$ docker run --name my-cont -d -p 8080:8080 ahmed/python-flask-docker
```

Now visit http://localhost:8080
```
 The hostname of the container is 6095273a4e9b and its IP is 172.17.0.2. 
```

### Verify the running container
Verify by checking the container ip and hostname (ID):
```
$ docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' my-cont
172.17.0.2
$ docker inspect -f '{{ .Config.Hostname }}' my-cont
6095273a4e9b
```


