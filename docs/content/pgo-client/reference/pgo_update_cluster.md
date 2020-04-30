---
title: "pgo update cluster"
---
## pgo update cluster

Update a PostgreSQL cluster

### Synopsis

Update a PostgreSQL cluster. For example:

    pgo update cluster mycluster --autofail=false
    pgo update cluster mycluster myothercluster --disable-autofail
    pgo update cluster --selector=name=mycluster --disable-autofail
    pgo update cluster --all --enable-autofail

```
pgo update cluster [flags]
```

### Options

```
      --all                               all resources.
      --cpu string                        Set the number of millicores to request for the CPU, e.g. "100m" or "0.1".
      --disable-autofail                  Disables autofail capabitilies in the cluster.
      --disable-memory-limit              Disables the PostgreSQL instances from being set with a memory limit on top of the memory request.
      --disable-pgbackrest-memory-limit   Disables the pgBackRest repository from being set with a memory limit on top of the memory request.
      --enable-autofail                   Enables autofail capabitilies in the cluster.
      --enable-memory-limit               Enables the PostgreSQL instances to be set with a memory limit on top of the memory request.
      --enable-pgbackrest-memory-limit    Enables the pgBackRest repository to be set with a memory limit on top of the memory request.
      --enable-standby                    Enables standby mode in the cluster(s) specified.
  -h, --help                              help for cluster
      --memory string                     Set the amount of RAM to request, e.g. 1GiB.
      --no-prompt                         No command line confirmation.
      --pgbackrest-cpu string             Set the number of millicores to request for CPU for the pgBackRest repository.
      --pgbackrest-memory string          Set the amount of Memory to request for the pgBackRest repository.
      --promote-standby                   Disables standby mode (if enabled) and promotes the cluster(s) specified.
  -s, --selector string                   The selector to use for cluster filtering.
      --shutdown                          Shutdown the database cluster if it is currently running.
      --startup                           Restart the database cluster if it is currently shutdown.
      --tablespace strings                Add a PostgreSQL tablespace on the cluster, e.g. "name=ts1:storageconfig=nfsstorage". The format is a key/value map that is delimited by "=" and separated by ":". The following parameters are available:
                                          
                                          - name (required): the name of the PostgreSQL tablespace
                                          - storageconfig (required): the storage configuration to use, as specified in the list available in the "pgo-config" ConfigMap (aka "pgo.yaml")
                                          - pvcsize: the size of the PVC capacity, which overrides the value set in the specified storageconfig. Follows the Kubernetes quantity format.
                                          
                                          For example, to create a tablespace with the NFS storage configuration with a PVC of size 10GiB:
                                          
                                          --tablespace=name=ts1:storageconfig=nfsstorage:pvcsize=10Gi
```

### Options inherited from parent commands

```
      --apiserver-url string     The URL for the PostgreSQL Operator apiserver that will process the request from the pgo client.
      --debug                    Enable additional output for debugging.
      --disable-tls              Disable TLS authentication to the Postgres Operator.
      --exclude-os-trust         Exclude CA certs from OS default trust store
  -n, --namespace string         The namespace to use for pgo requests.
      --pgo-ca-cert string       The CA Certificate file path for authenticating to the PostgreSQL Operator apiserver.
      --pgo-client-cert string   The Client Certificate file path for authenticating to the PostgreSQL Operator apiserver.
      --pgo-client-key string    The Client Key file path for authenticating to the PostgreSQL Operator apiserver.
```

### SEE ALSO

* [pgo update](/pgo-client/reference/pgo_update/)	 - Update a pgouser, pgorole, or cluster

###### Auto generated by spf13/cobra on 30-Apr-2020