# nfs-external-provisioner
NFS mount using dynamic volume and Storage Class

If you have an external NFS export and want to share that with a pod/deployment, you can leverage the nfs-subdir-external-provisioner to create a storageclass that can dynamically create the persistent volume.

```helm
helm repo add nfs-subdir-external-provisioner https://kubernetes-sigs.github.io/nfs-subdir-external-provisioner
```

In values.yml change above places
nfs:
  server: <server>
  path: <path>


```helm
helm template nfs-subdir-external-provisioner . | kubectl apply -f -
```