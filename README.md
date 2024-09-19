# wp_container

A docker compose environment for deploying Wordpress for developing and testing purposes.

## Usage

### Setup
Edit content of the .env file with the desired credentials, ports and other settings.

### Install
```
sudo sh wp-install.sh
```
Don't access the website before the next command, since the script will install WordPress for you. Wait 30 seconds approximately until the database starts, otherwise the initialization won't work.

### Initialize
```
sudo sh wp-init.sh
```


Thanks to @cosimoscarella for the work done, which helped to make this project work.
Forked from: https://github.com/cosimoscarcella/wordpress-installer
