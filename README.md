# NGINX Load balance methods (nginx.conf)

## Round Robin

```
upstream my_http_servers {
    server 127.0.0.1:4000;      # httpServer1 listens to port 4000
    server 127.0.0.1:4001;      # httpServer2 listens to port 4001
    server 127.0.0.1:4002;      # httpServer3 listens to port 4002
    server 127.0.0.1:4003;      # httpServer4 listens to port 4003
}
```

## Hash

```
upstream my_http_servers {
    hash $scheme$request_uri;
    server 127.0.0.1:4000;      # httpServer1 listens to port 4000
    server 127.0.0.1:4001;      # httpServer2 listens to port 4001
    server 127.0.0.1:4002;      # httpServer3 listens to port 4002
    server 127.0.0.1:4003;      # httpServer4 listens to port 4003
}
```

## IP Hash

```
upstream my_http_servers {
    ip_hash;
    server 127.0.0.1:4000;      # httpServer1 listens to port 4000
    server 127.0.0.1:4001;      # httpServer2 listens to port 4001
    server 127.0.0.1:4002;      # httpServer3 listens to port 4002
    server 127.0.0.1:4003;      # httpServer4 listens to port 4003
}
```

## Least connection

```
upstream my_http_servers {
    least_conn;
    server 127.0.0.1:4000;      # httpServer1 listens to port 4000
    server 127.0.0.1:4001;      # httpServer2 listens to port 4001
    server 127.0.0.1:4002;      # httpServer3 listens to port 4002
    server 127.0.0.1:4003;      # httpServer4 listens to port 4003
}
```
