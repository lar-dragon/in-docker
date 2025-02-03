Run commands in docker on local PWD by current user.

How to use:
```sh
in-docker CONTAINER COMMAND ...ARGUMENTS
```

For example:
```sh
in-docker php composer -v
```

Define PORTS varible (in EXTERNAL:INTERNAL ports number formats) for expose container ports, like:
```sh
PORTS=80:80,7000:7000 in-docker node --inspect=7000 --inspect-brk app.js
```

How to install:
1. clone into any local place
1. link that script to ~/.local/bin/in-docker
1. make simple scripts for nedded instruments in ~/.local/bin, like:
```sh
#!/bin/bash
in-docker node npm $@
```
