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

### nginx

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