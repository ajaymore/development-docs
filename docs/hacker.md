# Hacker

## Running a proxy

```
sudo apt update
sudo apt install squid
sudo nano /etc/squid/squid.conf
sudo apt-get install apache2-utils
sudo touch /etc/squid/passwd
sudo chown proxy: etc/squid/passwd
sudo htpasswd /etc/squid/passwd newuser
```

```
sudo systemctl restart squid
sudo systemctl status squid
sudo systemctl start squid
```

```
auth_param basic program /usr/lib/squid/basic_ncsa_auth /etc/squid/passwd
auth_param basic realm proxy
acl authenticated proxy_auth REQUIRED
http_access allow authenticated
http_port 3128 transparent
```
