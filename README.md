# Supported tags and respective `Dockerfile` links

- `0.2.9.9`, `stable`, `latest` [(Dockerfile)](https://github.com/consatan/docker_tor_clientonly/blob/0.2.9.9/Dockerfile)

# Docker Tor project

Dockerfile to install [Tor project](https://www.torproject.org/), running as a SOCKS5 server on port **9050**. It's running on `ClientOnly` mode.

### Install

#### Pull from Docker repository

```bash
$ docker pull consatan/tor
```

#### Building from Dockerfile

```bash
$ git clone https://github.com/consatan/docker_tor_clientonly
$ cd docker_tor_clientonly
$ docker build . -t consatan/tor
```

### How to use

#### Run

```bash
$ docker run -d --name tor_instance -p 127.0.0.1:9050:9050 consatan/tor
```

#### Proxy

```bash
# return your external ip
$ curl http://httpbin.org/ip
# return exit node ip
$ curl -x socks5h://127.0.0.1:9050 http://httpbin.org/ip
```

#### View log

```bash
$ docker log tor_instance
```

#### Stop

```bash
$ docker stop tor_instance
```

### Reference

- [np1/docker-tor-clientonly](https://github.com/np1/docker-tor-clientonly)
