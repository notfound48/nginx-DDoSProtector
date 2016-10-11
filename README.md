### Instalation

Clone repository to nginx config folder 

mkdir -p /etc/nginx/DDoSProtector && cd /etc/nginx/DDoSProtector && git clone http://git.skillum.ru/git/server-admin.ddosprotector ./

Include  DDoSProtector/DDoSProtector.conf in your nginx.conf

### Configure

In config file set server_name variable to protect hosts names;

Configure block_user_agent and block_ip files;

Change listen port and address (default 127.0.0.1:81) in protect hosts configurations;

Add rule:

 deny all;
 allow 127.0.0.1;
