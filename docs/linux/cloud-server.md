# Server configuration

## Server provisioning

## SSH access

## Port access and DNS management

## Credential management

## Packages

### Base packages
- `sudo apt update && sudo apt dist-upgrade && sudo apt autoremove`
- `sudo apt -y install gcc make linux-headers-$(uname -r) dkms`
- `sudo apt install -y build-essential autoconf automake python-dev curl`

### Docker

### Networking with nginx

- [Lets encrypt](https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-16-04)
- [Virtual Host](https://www.digitalocean.com/community/tutorials/how-to-set-up-nginx-server-blocks-virtual-hosts-on-ubuntu-16-04)

1. Install nginx
```
cd /etc/nginx/sites-available
sudo mv default mysite.org
sudo vim mysite.org
sudo rm /etc/nginx/sites-enabled/default
sudo ln -s /etc/nginx/sites-available/mysite.org /etc/nginx/sites-enabled/mysite.org
sudo nginx -t
sudo systemctl restart nginx
sudo certbot --nginx -d mysite.org -d www.mysite.org
```

### apache2
```
# create conf file -> lms.abc.com -> provide docker proxy pass
# get conf to work with application on http
# get conf to work with application on https
moodle, wordpress, nodejs app

```
## Maintenance

### DB Backup & Restore

### Automation scripts

## Load balancing

## Digital ocean
https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-16-04
https://www.digitalocean.com/community/tutorials/7-security-measures-to-protect-your-servers
https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys--2
https://www.digitalocean.com/community/tutorials/how-to-setup-a-firewall-with-ufw-on-an-ubuntu-and-debian-cloud-server

### SSH Keys
```
ssh-keygen -t rsa -C "mail@ajaymore.in"
create droplet with above key
ssh -i ~/.ssh/id_rsa root@ip_address
adduser sammy
usermod -aG sudo sammy

sudo nano /etc/ssh/sshd_config
	PermitRootLogin no
	PasswordAuthentication no
mkdir ~/.ssh
chmod 700 ~/.ssh
nano ~/.ssh/authorized_keys
chmod 600 ~/.ssh/authorized_keys
sudo systemctl reload sshd.service
```
-- Make sure to test the user acces without exiting

### Firewalls
```
sudo apt-get install ufw
sudo ufw status
sudo vi /etc/default/ufw
IPV6=yes
sudo ufw disable
sudo ufw enable
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow ssh
sudo ufw allow 22/tcp
sudo ufw allow www
```

### 
