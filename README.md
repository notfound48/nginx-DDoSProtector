# NGINX DDoS Protector

Configuration of nginx virtual host for protect of DDoS attacks. 

## Installation

Clone repository to nginx config folder:

```bash
cd /etc/nginx && git clone http://git.skillum.ru/git/server-admin.ddosprotector DDoSProtector
```

Include  `DDoSProtector/DDoSProtector.conf` in your `nginx.conf`

## Configure
In config file set `server_name` variable to protect hosts names.

Configure `block_user_agent` and `block_ip` files.

Change listen port and address (default 127.0.0.1:81) in protect hosts configurations.

Add rule in protect hosts configurations:
```nginx
deny all;
allow 127.0.0.1;
```