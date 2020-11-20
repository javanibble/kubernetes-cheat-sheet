# Minikube 
minikube quickly sets up a local Kubernetes cluster on macOS, Linux, and Windows. 


## Table of Contents
* [Minikube Commands](#minikube-commands)
* [Minikube Tutorials](#minikube-tutorials)
* [Resources](#resources)

## Minikube Commands

### Minikube Command Overview
**Basic Commands:**
* `minikube start` - Starts a local Kubernetes cluster ([Reference](https://minikube.sigs.k8s.io/docs/commands/start/))
* `minikube status` - Gets the status of a local Kubernetes cluster ([Reference](https://minikube.sigs.k8s.io/docs/commands/status/))
* `minikube stop` - Stops a running local Kubernetes cluster ([Reference](https://minikube.sigs.k8s.io/docs/commands/stop/))
* [`minikube delete`](#minikube-delete) - Deletes a local Kubernetes cluster ([Reference](https://minikube.sigs.k8s.io/docs/commands/delete/))
* `minikube dashboard` - Access the Kubernetes dashboard running within the minikube cluster ([Reference](https://minikube.sigs.k8s.io/docs/commands/dashboard/))
* `minikube pause` - Pause Kubernetes ([Reference](https://minikube.sigs.k8s.io/docs/commands/pause/))
* `minikube unpause` - Unpause Kubernetes ([Reference](https://minikube.sigs.k8s.io/docs/commands/unpause/))

**Images Commands:**
* `minikube docker-env` - Configure environment to use minikube's Docker daemon ([Reference](https://minikube.sigs.k8s.io/docs/commands/docker-env/))
* `minikube podman-env` - Configure environment to use minikube's Podman service ([Reference]())
* `minikube cache` - Add, delete, or push a local image into minikube ([Reference](https://minikube.sigs.k8s.io/docs/commands/cache/))

**Configuration and Management Commands:**
* `minikube addons` - Enable or disable a minikube addon ([Reference](https://minikube.sigs.k8s.io/docs/commands/addons/))
* `minikube config` - Modify persistent configuration values ([Reference](https://minikube.sigs.k8s.io/docs/commands/config/))
* `minikube profile` - Get or list the current profiles (clusters) ([Reference](https://minikube.sigs.k8s.io/docs/commands/profile/))
* `minikube update-context` - Update kubeconfig in case of an IP or port change ([Reference](https://minikube.sigs.k8s.io/docs/commands/update-context/))

**Networking and Connectivity Commands:**
* `minikube service` - Returns a URL to connect to a service ([Reference](https://minikube.sigs.k8s.io/docs/commands/service/))
* `minikube tunnel` - Connect to LoadBalancer services ([Reference](https://minikube.sigs.k8s.io/docs/commands/tunnel/))

**Advanced Commands:**
* `minikube mount` - Mounts the specified directory into minikube ([Reference](https://minikube.sigs.k8s.io/docs/commands/mount/))
* `minikube ssh` - Log into the minikube environment (for debugging) ([Reference](https://minikube.sigs.k8s.io/docs/commands/ssh/))
* `minikube kubectl` - Run a kubectl binary matching the cluster version ([Reference](https://minikube.sigs.k8s.io/docs/commands/kubectl/))
* `minikube node` - Add, remove, or list additional nodes ([Reference](https://minikube.sigs.k8s.io/docs/commands/node/))

**Troubleshooting Commands:**
* `minikube ssh-key` - Retrieve the ssh identity key path of the specified cluster ([Reference](https://minikube.sigs.k8s.io/docs/commands/ssh-key/))
* `minikube ip` - Retrieves the IP address of the running cluster ([Reference](https://minikube.sigs.k8s.io/docs/commands/ip/))
* `minikube logs` - Returns logs to debug a local Kubernetes cluster ([Reference](https://minikube.sigs.k8s.io/docs/commands/logs/))
* `minikube update-check` - Print current and latest version number ([Reference](https://minikube.sigs.k8s.io/docs/commands/update-check/))
* [`minikube version`](#minikube-version) - Print the version of minikube ([Reference](https://minikube.sigs.k8s.io/docs/commands/version/))

**Other Commands:**
* `minikube completion` - Generate command completion for a shell ([Reference](https://minikube.sigs.k8s.io/docs/commands/completion/))
* `minikube help` - Help about any command ([Reference](https://minikube.sigs.k8s.io/docs/commands/help/))
* `minikube options` - Show a list of global command-line options (applies to all commands) ([Reference](https://minikube.sigs.k8s.io/docs/commands/options/))


### Minikube Command Examples

#### minikube delete  

```shell
# Deletes a local Kubernetes cluster
$ minikube delete

# Deletes a local Kubernetes cluster & delete all profiles
$ minikube delete --all

# Deletes a local Kubernetes cluster & delete the '.minikube' folder from your user directory.
$ minikube delete --purge
```

#### minikube version  
```shell
# Print the version 
$ minikube version
```

## Minikube Tutorials
### Minikube Basic Startup


```shell
$ minikube start
```


## Resources
* [Youtube - Minikube Intro](https://www.youtube.com/watch?v=4x0CZmF_U5o)