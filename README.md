# tor-relay

## Usage

### Set up your config manually on your host file system

```
mkdir -p /srv/tor/etc/tor
mkdir -p /srv/tor/var/lib/tor
useradd -u 9001 -g 9001 tor
chown -R tor:tor /srv/tor/var/lib/tor
echo 'ORPort 80' >> /srv/tor/etc/tor/torrc
echo 'ExitPolicy reject *:*' >> /srv/tor/etc/tor/torrc
```

```
docker run -p 80:80 -p 443:443 -v /srv/tor/etc/tor:/etc/tor -v /srv/tor/var/lib/tor:/var/lib/tor aianus/tor-relay
```

## Persisting the Relay's Key

Your relay's key will be stored in the volume mounted ad /var/lib/tor
