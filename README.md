## Steps to reproduce

#### create networks
```
podman network create netA --subnet 10.93.0.0/24 --gateway 10.93.0.1 --dns 10.93.0.53
podman network create netB --subnet 10.89.0.0/24 --gateway 10.89.0.1 --dns 10.89.0.53
```

#### Start containers
```
podman compose up -d
```

### Exec into container and resolve names
```
podman exec -it $(podman ps -qf "name=tester") sh

nslookup myapp.test
nslookup service.test
```




