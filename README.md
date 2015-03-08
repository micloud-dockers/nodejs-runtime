# Node.js Runtime

The final target is to build a image for running the local web site. Like:

```
docker run -d \
  -p [external-port]:[internal-port] \
  -v [external-path]:[internal-path] \
  [my-image]
```

## Sample

### Prepare the node.js code

```
$ express -e ~/project/web
$ cd ~/project/web && npm install
```

### Test the code locally

```
$ cd ~/project/web
$ npm start
```

### Run the application folder

```
docker run -d -p 3000:3000 -v ~/project/dockerws/web:/data peihsinsu/nodejs-runtime
```

### Debug

If run the docker error without error return, you can use "docker logs" to show the execute message in instance.

```
docker logs [your-docker-id]
```

If your instance success running, you can use "-f" parameter to show log like "tail -f".

```
docker logs -f [your-docker-id]
```

