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
1. Create a droplet without ssh
2. create ssh key `ssh-keygen`
3. create user on the server
```
ssh root@ip_address
adduser sammy
usermod -aG sudo sammy

# copy public key from the local machine
vim ~/.ssh/authorized_keys
chmod 600 ~/.ssh/authorized_keys

# disable password authentication
sudo nano /etc/ssh/sshd_config
  PasswordAuthentication no
  PubkeyAuthentication yes
  ChallengeResponseAuthentication no
  
sudo systemctl reload sshd

# firewall
sudo ufw app list
sudo ufw allow OpenSSH
sudo ufw enable
sudo ufw status
```
