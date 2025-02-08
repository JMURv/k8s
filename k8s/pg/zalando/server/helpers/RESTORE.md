There is also a possibility to restore a database without cloning it. The advantage to this is that there is no need to change anything on the application side. However, as it involves deleting the database first, this process is of course riskier than cloning (which involves adjusting the connection parameters of the app).

First, make sure there is no writing activity on your DB, and save the UID. Then delete the postgresql K8S resource:

```shell
kubectl delete postgresql cluster-name
```

Then deploy a new manifest with the same name, referring to itself (both name and UID) in the clone section:

```yaml 
metadata:
    name: acid-minimal-cluster
    [...]
spec:
    [...]
    clone:
        cluster: "acid-minimal-cluster"  # the same as metadata.name above!
        uid: "<original_UID>"
        timestamp: "2022-04-01T10:11:12.000+00:00"
```
This will create a new database cluster with the same name but different UID, whereas the database will be in the state it was at the specified time.