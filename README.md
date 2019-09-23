# dev-env
_A development environment built upon docker._

## overview
The intention of this project is to provide the necessary tools and packages required for a standard golang development environment which is convenient and accessible. The dev-env is built upon the an [alpine 3.10 golang image](https://hub.docker.com/_/golang), this includes the following tools/packages:
- [golang](https://golang.org/)
- [groovy](http://groovy-lang.org/)
- [git](https://git-scm.com/)
- [hub](https://github.com/github/hub)
- [vi](https://www.vim.org/)
  - [golang plugin](https://github.com/fatih/vim-go)
  - [buffer switcher](https://github.com/manniwood/vim-buf)
  - [groovy syntax highlighting](https://github.com/vim-scripts/groovy.vim)
- [gcloud](https://cloud.google.com/sdk/gcloud/)
- [helm](https://helm.sh/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- [jx](https://github.com/jenkins-x/jx)
- [dep](https://github.com/golang/dep)
- [ko](https://github.com/google/go-containerregistry/tree/master/cmd/ko)
- [delve](https://github.com/go-delve/delve)
- [pre-commit](https://pre-commit.com/)
#### IDE
- [GoLand](docs/goland.md)

## support
The dev-env has only been verified on **MacOS**. It should _execute_ on other operating systems capable of running docker containers, but you may encounter issues.

## prerequisites
You'll need [Docker](https://www.docker.com/) to use the dev-env, see [Docker for MacOS](https://hub.docker.com/editions/community/docker-ce-desktop-mac).

## build
Use the following command to build the docker image locally:
```
make build
```

## run
### TMUX
To execute the dev-env, perform the following:
```
$ git clone https://github.com/jenkins-x/dev-env
$ cd dev-env
$ ./dev-env
```
### NO TMUX
```
$ git clone https://github.com/jenkins-x/dev-env
$ cd dev-env
$ ./dev-env no-tmux
```

## tmux
This environment uses tmux to manage its window sessions. The environment is configured with the configuration from [here](https://github.com/gpakosz/.tmux), so a big thank you to [Gregory Pakosz](https://github.com/gpakosz) for the tmux configuration). The tmux key bindings can be found [here](https://github.com/gpakosz/.tmux#bindings), with the exception of the **horizontal split** _below_ (overridden within the environments `.tmux.conf.local` file):
- `<prefix> \` splits the current pane horizontally
