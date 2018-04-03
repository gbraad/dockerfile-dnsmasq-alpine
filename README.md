# Simple container running `dnsmasq` on Alpine


The daemon will read all files in the volume mounted to `/etc/dnsmasq.hosts`

```
$ docker run \
    --name dnsmasq \
    --cap-add=NET_ADMIN \
    -v $(pwd)/dnsmasq.hosts:/etc/dnsmasq.hosts \
    -p 127.0.0.10:53:53/udp \
    -d gbraad/dnsmasq-alpine
```

Overwrite the used configuration

```
$ docker run \
    --name dnsmasq \
    --cap-add=NET_ADMIN \
    -v $(pwd)/dnsmasq.conf:/etc/dnsmasq.conf \
    -p 127.0.0.10:53:53/udp \
    -d gbraad/dnsmasq-alpine
```
