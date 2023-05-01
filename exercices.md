# Edit containers config file to add secure and insecure registry

```sh
vi /etc/containers/registries.conf
```
#

podman pull [image:tag]

#

podman run -d --name=[container_name] -v [host_paht]:[container_path]/:Z --pod [pod_name] [image:tag]

#

podman logs [container_name] > [file_name].log

# Crete a path with selinux context for container

```sh
mkdir -pv [path]
sudo semange -a t container_file_t '[path](/.*)?'
sudo restorecon -R [path]
podman unshare chown -Rv 27:27  [path] 
```

podman run -d --name=[name] -e MY_SQL


