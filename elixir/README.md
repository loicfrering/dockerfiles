Elixir Dockerfile
=================

Elixir is a dynamic, functional language that leverages the Erlang VM.

Usage
-----

```
docker run -it --rm loicfrering/elixir elixir --version
```

Binstub
-------

Mix:

```
#!/usr/bin/env bash
set -e
docker run -it --rm -u $(id -u):$(id -g) -v $HOME/.mix:$HOME/.mix -v $HOME/.hex:$HOME/.hex -e "HOME=$HOME" -v $PWD:/work -p 4000:4000 loicfrering/elixir elixir --erl "-smp disable" /usr/local/bin/mix $@
```
