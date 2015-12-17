Rust Dockerfile
===============

Rust is a systems programming language that runs blazingly fast.

Usage
-----

```
docker run -it --rm loicfrering/rust rustc --version
```

Binstub
-------

Cargo:

```
#!/usr/bin/env bash
set -e
docker run -it --rm -u $(id -u):$(id -g) -v $HOME/.cargo:$HOME/.cargo -e "HOME=$HOME" -v $PWD:/work -p 3000:3000 loicfrering/rust cargo $@
```
