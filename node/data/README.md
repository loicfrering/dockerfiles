Node Data Dockerfile
====================

Creation
--------

```
$ docker build -t loicfrering/nodedata .
$ docker create --name nodedata loicfrering/nodedata /bin/true
```

Usage
-----

Example binstub:

```
#!/usr/bin/env bash
set -e
docker run \
  -it --rm \
  -u $(id -u):$(id -g) \
  --volumes-from nodedata \
  -e "NPM_CONFIG_PREFIX=/nodedata" \
  -e "NPM_CONFIG_CACHE=/nodedata/npm-cache" \
  -e "PATH=$PATH:/nodedata/bin" \
  -v $PWD:/work \
  -w /work \
  -p 4000:4000 \
  node \
  npm $@
```
