# wp_container

A docker compose environment for deploying Wordpress for developing and testing purposes.

## Usage

### Setup
Edit the bin/install.sh file and set the correct url (IP address) for wordpress. Then, edit content of the .env file with the desired credentials, ports and other settings.

### Install
```
sudo sh wp-install.sh
```
**Don't access the website before the next command, since the script will install WordPress for you**. Wait 30 seconds approximately until the database starts, otherwise the initialization won't work.

### Initialize
```
sudo sh wp-init.sh
```

## Developing a plugin
If you want to use this instance to develop a plugin, you can paste or create the plugin folder in the root path of this repo (same path as `docker-compose.yml`) and uncomment the plugin volume mapping in the docker-compose.yml file under the wordpress service. Then, replace `PLUGIN-NAME` with the name of your plugin folder.

## Troubleshooting
If for some reason the instance doesn't start or returns permissions errors when trying to connect to mysql, explicitly removing the volumes is the way to go:
```
docker stop $(docker ps -aq)
docker rm $(docker ps -aq)

docker volume rm db_data
docker volume rm wp_data
```
**Keep in mind that this deletes all the persistent data from the volumes**. After this, proceed with install again.

Thanks to @cosimoscarella for the work done, which helped to the creation of this project.
Forked from: https://github.com/cosimoscarcella/wordpress-installer
