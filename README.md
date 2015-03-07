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
