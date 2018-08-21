# Oracle Docker image


# Build the image

If you'd like to try directly from the Dockerfile you can build the image as:

```
docker build  -t oracle:latest .
```
# Pull the image

The image is also released as an official Docker image from Docker's automated build repository - you can always pull or refer the image when launching containers.

```
docker pull brpedromaia/oracle
```

# Start a container

In order to use the Docker image you have just build or pulled use:

```
docker run -itd --name=oracle oracle
```

**Make sure that SELinux is disabled on the host. If you are using boot2docker you don't need to do anything.**

```
docker run -it --name=oracle oracle -bash
```

** you would like to have a tunnel port exposed to localhost.**

```
docker run -itd --name=oracle oracle -p 8080:8080 -p 1521:1521
```

## Testing

You can run one of the stock examples:

```
docker exec -it brpedromaia/oracle bash
echo "select 1 from dual;" |sqlplus system/oracle

or

http://localhost:8080/apex
workspace: INTERNAL
user: ADMIN
password: oracle
```

## Client config 
```
    hostname: localhost
    port: 1521
    sid: xe
    username: system
    password: oracle
```


## Automate everything

To automate everything add code into "entrypoint.sh"
