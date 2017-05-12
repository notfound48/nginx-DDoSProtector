# NGINX DDoS Protector

Configuration of nginx virtual host for protect of DDoS attacks. 

## Installation

Clone repository to nginx config folder:

```bash
cd /etc/nginx && git clone https://github.com/notfound48/nginx-DDoSProtector.git
```

Include  `nginx-DDoSProtector/*.conf` in your `nginx.conf`

## Configure
Configure the protective layer for your virtual post by following the example in the file 00_layer_www.example.com.conf
The file name of the protective layer configuration must be *.conf

Set variables 

    set $ddosp_use_cache off; # Use caching for ptotected hosts (on|off)
    set $ddosp_use_limits on; # Use limits for ptotected hosts (on|off)
    
## Configure SSL support
1. Prepare dir with SSL

```bash
mkdir /etc/nginx/ssl
chown root:root /etc/nginx/ssl
chmod 700 /etc/nginx/ssl
cd /etc/nginx/ssl
```

2. Generate Diffie-Hellmar parameters:

```bash
openssl dhparam -out /etc/nginx/ssl/dhparam.pem 2048
chmod 400 /etc/nginx/ssl/*
```

3. Uncomment all SSL section

If you have several virtual hosts with SSL that are protected, then for each of them you need to create a protective layer. If you have several virtual hosts without SSL that are protected, you can create one layer with the parameter: ```nginx server_name _;```

Configure `block_user_agent` and `block_ip` files.

Change listen port and address (default 127.0.0.1:81) in protect hosts configurations.

Add rule in protect hosts configurations:
```nginx
deny all;
allow 127.0.0.1;
```
