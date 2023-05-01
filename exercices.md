# Edit containers config file to add secure and insecure registry

```sh
vi /etc/containers/registries.conf
```
# Pull image

```sh
podman pull [image:tag]
```

# Init a container with volume

```sh
podman run -d --name=[container_name] -v [host_paht]:[container_path]/:Z --pod [pod_name] [image:tag]
```

# See logs

```sh
podman logs [container_name] > [file_name].log
```

# Crete a Pod with env_vars

```sh
podman run -d --name=[container_name] -e [ENV_VAR_KEY]=[env_var_value] -p [host_port]:[container_pod] [image:tag]
```
# Copy files to container

```sh
podman cp [container_name]:[container_path_file] [local_path]
```

# Crete a path with selinux context for container

```sh
mkdir -pv [path]
sudo semange -a t container_file_t '[path](/.*)?'
sudo restorecon -R [path]
podman unshare chown -Rv 27:27  [path] 
```

podman run -d --name=[name] -e MY_SQL


