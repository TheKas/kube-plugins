# kube-plugins
a repository for plugins and scripts for kubernetes

# Pre-requisites
* kubectl >= 1.12.x
* tmux >= 2.1
(Tmux is a terminal multiplexer that helps in creating multiple terminals.)

# Installation
* git clone https://github.com/abhiTamrakar/kube-plugins.git
* cd kube-plugins

## USAGE
* TO use as K8S Plugin, name convention is kubectl-plugin name-argument. Follow https://kubernetes.io/docs/tasks/extend-kubectl/kubectl-plugins/ for more detail.
* Copy the plugin script to /usr/local/bin/
* Follow naming convention as per the kubectl-plugins document mentioned above.
* Run below command to see available plugins
```
# run command and if kmux is not listed as plugins, follow below.

$ kubectl plugin list

# install plugin as recommended.

cd kube-plugins

cp -p kmux/kmux /usr/local/bin/kubectl-kmux

cp -p krawl/krawl /usr/local/bin/kubectl-krawl

# run list command again to see if your plugin is listed.

$ kubectl plugin list

The following compatible plugins are available:

/usr/local/bin/kubectl-krawl

/usr/local/bin/kubectl-kmux

```

* Execute
```
$ kubectl krawl

---------------------------------------------------------------------------------
  Krawl is a command line utility to scan pods and prints name of errored pods
+and containers within. To use it as kubernetes plugin, please check their page
=================================================================================
NAMESPACE    |POD_NAME                     |CONTAINER_NAME      |ERRORS
---------    |--------                     |--------------      |------
kube-system  |kube-addon-manager-minikube  |kube-addon-manager  |3

```

* To use as utility script, use as is.

```
$ krawl

---------------------------------------------------------------------------------
  Krawl is a command line utility to scan pods and prints name of errored pods
+and containers within. To use it as kubernetes plugin, please check their page
=================================================================================
NAMESPACE    |POD_NAME                     |CONTAINER_NAME      |ERRORS
---------    |--------                     |--------------      |------
kube-system  |kube-addon-manager-minikube  |kube-addon-manager  |3

```
