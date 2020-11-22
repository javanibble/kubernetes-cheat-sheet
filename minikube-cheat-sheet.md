<img
  src="https://miro.medium.com/max/400/0*KzqL3xqmXzV5PPjX.png"
  width="300"
  align="right"
/>

# Minikube 
minikube quickly sets up a local Kubernetes cluster on macOS, Linux, and Windows. 


## Table of Contents
* [Minikube Commands](#minikube-commands)
* [Minikube Tutorials](#minikube-tutorials)
* [Resources](#resources)

## Minikube Commands

### Minikube Command Overview
**Basic Commands:**
* [`minikube start`](#minikube-start) - Starts a local Kubernetes cluster ([Reference](https://minikube.sigs.k8s.io/docs/commands/start/))
* [`minikube status`](#minikube-status) - Gets the status of a local Kubernetes cluster ([Reference](https://minikube.sigs.k8s.io/docs/commands/status/))
* [`minikube stop`](#minikube-stop) - Stops a running local Kubernetes cluster ([Reference](https://minikube.sigs.k8s.io/docs/commands/stop/))
* [`minikube delete`](#minikube-delete) - Deletes a local Kubernetes cluster ([Reference](https://minikube.sigs.k8s.io/docs/commands/delete/))
* [`minikube dashboard`](#minikube-dashboard) - Access the Kubernetes dashboard running within the minikube cluster ([Reference](https://minikube.sigs.k8s.io/docs/commands/dashboard/))
* [`minikube pause`](#minikube-pause) - Pause Kubernetes ([Reference](https://minikube.sigs.k8s.io/docs/commands/pause/))
* [`minikube unpause`](#minikube-unpause) - Unpause Kubernetes ([Reference](https://minikube.sigs.k8s.io/docs/commands/unpause/))

**Images Commands:**
* `minikube docker-env` - Configure environment to use minikube's Docker daemon ([Reference](https://minikube.sigs.k8s.io/docs/commands/docker-env/))
* `minikube podman-env` - Configure environment to use minikube's Podman service ([Reference]())
* [`minikube cache`](#minikube-cache ) - Add, delete, or push a local image into minikube ([Reference](https://minikube.sigs.k8s.io/docs/commands/cache/))

**Configuration and Management Commands:**
* `minikube addons` - Enable or disable a minikube addon ([Reference](https://minikube.sigs.k8s.io/docs/commands/addons/))
* `minikube config` - Modify persistent configuration values ([Reference](https://minikube.sigs.k8s.io/docs/commands/config/))
* `minikube profile` - Get or list the current profiles (clusters) ([Reference](https://minikube.sigs.k8s.io/docs/commands/profile/))
* `minikube update-context` - Update kubeconfig in case of an IP or port change ([Reference](https://minikube.sigs.k8s.io/docs/commands/update-context/))

**Networking and Connectivity Commands:**
* [`minikube service`](#minikube-service) - Returns a URL to connect to a service ([Reference](https://minikube.sigs.k8s.io/docs/commands/service/))
* `minikube tunnel` - Connect to LoadBalancer services ([Reference](https://minikube.sigs.k8s.io/docs/commands/tunnel/))

**Advanced Commands:**
* `minikube mount` - Mounts the specified directory into minikube ([Reference](https://minikube.sigs.k8s.io/docs/commands/mount/))
* `minikube ssh` - Log into the minikube environment (for debugging) ([Reference](https://minikube.sigs.k8s.io/docs/commands/ssh/))
* `minikube kubectl` - Run a kubectl binary matching the cluster version ([Reference](https://minikube.sigs.k8s.io/docs/commands/kubectl/))
* `minikube node` - Add, remove, or list additional nodes ([Reference](https://minikube.sigs.k8s.io/docs/commands/node/))

**Troubleshooting Commands:**
* `minikube ssh-key` - Retrieve the ssh identity key path of the specified cluster ([Reference](https://minikube.sigs.k8s.io/docs/commands/ssh-key/))
* [`minikube ip`](#minikube-ip) - Retrieves the IP address of the running cluster ([Reference](https://minikube.sigs.k8s.io/docs/commands/ip/))
* [`minikube logs`](#minikube-logs) - Returns logs to debug a local Kubernetes cluster ([Reference](https://minikube.sigs.k8s.io/docs/commands/logs/))
* [`minikube update-check`](#minikube-update-check) - Print current and latest version number ([Reference](https://minikube.sigs.k8s.io/docs/commands/update-check/))
* [`minikube version`](#minikube-version) - Print the version of minikube ([Reference](https://minikube.sigs.k8s.io/docs/commands/version/))

**Other Commands:**
* `minikube completion` - Generate command completion for a shell ([Reference](https://minikube.sigs.k8s.io/docs/commands/completion/))
* `minikube help` - Help about any command ([Reference](https://minikube.sigs.k8s.io/docs/commands/help/))
* `minikube options` - Show a list of global command-line options (applies to all commands) ([Reference](https://minikube.sigs.k8s.io/docs/commands/options/))


### Minikube Command Examples


#### minikube addons

```shell
# Lists all available minikube addons as well as their current statuses
$ minikube addons list

# Disables the addon `dashboard` within minikube.
$ minikube addons disable dashboard

# Enables the addon `dashboard` within minikube.
$ minikube addons enable dashboard

# Enables the addon `metrics-server` within minikube.
$ minikube addons enable metrics-server

# Open the dashboard addon in a browser, since it exposes a browser endpoint.
$ minikube addons open dashboard
```

#### minikube cache  
Add, delete, or push a local image into minikube. See the `~/.minikube/cache/images` directory.

```shell
# List all the available images from the local cache.
$ minikube cache list

# Add the latest version of the nginx image to the local cache.
$ minikube cache add nginx:latest

# Reload the latest version of the nginx image to the local cache.
$ minikube cache reload nginx:latest

# Delete the latest vesrion of the nginx image from the local cache.
$ minikube cache delete nginx:latest
```

#### minikube dashboard
```shell
# Access the Kubernetes dashboard running within the minikube cluster
$ minikube dashboard

# Display dashboard URL instead of opening a browser
$ minikube dashboard --url
```

#### minikube delete  
```shell
# Deletes a local Kubernetes cluster
$ minikube delete

# Deletes a local Kubernetes cluster & delete all profiles
$ minikube delete --all

# Deletes a local Kubernetes cluster & delete the '.minikube' folder from your user directory.
$ minikube delete --purge
```

#### minikube ip
```shell
# Retrieves the IP address of the running cluster, and writes it to STDOUT.
$ minikube ip
```

#### minikube logs
```shell
# Gets the logs of the running instance, used for debugging minikube, not user code.
$ minikube logs

# Display the logs of the running instance and continously print new entries
$ minikube logs -f
```

#### minikube pause
```shell
# Pause the Kubernetes cluster
$ minikube pause
```

#### minikube service
```shell
# List the kubernetes URLs for the services in the local cluster. This is the same as `kubectl get svc -A`
$ minikube service list
```

#### minikube start  
```shell
# Starts a local Kubernetes cluster 
$ minikube start

# Starts a local Kubernetes cluster with a profile name allowing multiple instances of minikube independently. (default "minikube")
$ minikube start --profile my-profile-name

# Starts a local kubernetes cluster and enable the metrics-server and dashboard addons at start-up.
$ minikube start --addons metrics-server --addons dashboard

# Starts a local kubernetes cluster with one of the drivers: virtualbox, parallels, vmwarefusion, hyperkit, vmware, docker, podman (experimental) (defaults to auto-detect)
$ minikube start --driver='hyperkit'
```

#### minikube status
```shell
# Gets the status of a local Kubernetes cluster.
$ minikube status
```

#### minikube stop
```shell
# Stops a local Kubernetes cluster. This command stops the underlying VM or container, but keeps user data intact.
$ minikube stop
```

#### minikube unpause
```shell
# Unpause the Kubernetes cluster
$ minikube unpause
```

#### minikube update-check
```shell
# Print current and latest version number of minikube
$ minikube update-check
```

#### minikube version  
```shell
# Print the version of minikube
$ minikube version

# Print the version of minikube in yaml format
$ minikube version --output='yaml'

# Print the version of minikube in json format
$ minikube version --output='json'
```

## Minikube Tutorials
### Minikube Basic Startup


```shell
$ minikube start
$ minikube status
$ ps -Af | grep hyperkit
$ kubectl get po -A
$ kubectl get pods --all-namespaces

// Create a deployment
$ kubectl create deployment my-first-minikube --image=k8s.gcr.io/echoserver:1.4
$ kubectl get deployment 
$ kubectl edit deployment my-first-minikube
$ kubectl expose deployment my-first-minikube --type=LoadBalancer --port=8080
$ kubectl edit svc my-first-minikube
$ kubectl get svc

$ minikube ip
$ curl <ip>:<port>

// Remove deployment
$ kubectl delete svc my-first-minikube
$ kubectl delete deployment my-first-minikube
$ minikube stop
$ minikube delete
$ ps -Af | grep hyperkit
$ ps -ax | grep hyperkit
```

## Resources
* [Minikube GitHub Repository](https://github.com/kubernetes/minikube)
* [Youtube - Minikube Intro](https://www.youtube.com/watch?v=4x0CZmF_U5o)
* [A Cloud Guru - Minikube in the cloud on Ubuntu](https://acloudguru.com/course/minikube-in-the-cloud-on-ubuntu)