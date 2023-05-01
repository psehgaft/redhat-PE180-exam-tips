# Edit containers config file to add secure and insecure registry

```sh
vi /etc/containers/registries.conf
```

# Crete a path with selinux context for container

```sh
mkdir -pv [path]
sudo semange -a t container_file_t '[path](/.*)?'
sudo restorecon -R [path]
podman unshare chown -Rv 27:27  [path] 
```




