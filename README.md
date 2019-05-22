# Example Nginx Proxy in Docker

This uses [christhomas/nginx-proxy](https://github.com/christhomas/nginx-proxy) which is a fork of [jwilder/nginx-proxy](https://github.com/jwilder/nginx-proxy) with [adds support](https://github.com/jwilder/nginx-proxy/pull/1257) for a `VIRTUAL_PATH` environment variable that allows multiple upstream containers for the same domain, routing based on the path.

## Usage

Modiy your `/etc/hosts` file with:

```
# Testing nginx proxy
127.0.0.1 nginx-proxy.test
```

Then from your terminal:

```
$ ./generate-certs
$ docker-compose up -d
```

You should now be able to visit [https://nginx-proxy.test](https://nginx-proxy.test) and see links to the 2 upstreams on different paths.

There will be a warning about an invalid SSL cert as it's self-signed, but safe to ignore for this demo.
