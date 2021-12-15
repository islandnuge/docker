# frontalnugity/docker
A generic docker configuration for all web projects intended for sterotypical web app development in Laravel under a TALL stack.

## Dependencies:
Intended as a clean setup for typical laravel/php development:
- Nginx
- MySQL 8.0
- PHP 8.

## Installation / Usage
Clone it into your project as `/docker` using the command below and modify the configuration files per your preference.

```bash
git clone git@github.com:frontalnugity/docker
```

This will include the docker config as a sub-module to your project. If you wish to add it to your parent github repo as just code, you can disconnect the submodule dependency by running

```bash
rm -rf .git
```

Database and mysql settings are specified in .env. If you are using this in a Laravel environment, run the following command to update the env settings to reference values in your laravel .env

```bash
rm .env; 
ln -s ../.env .env;
```

The `docker-compose.yml` file uses a generic network name, prior to running `docker compose up` it is recommend you replace qq`networkname` with a more descriptive name for your project.

Setup assumes that your working directory (inside your containers) for your web-app will be:
```bash
/application
```

Persistent data (MySql, associated logs ) will be created/stored in:
```bash
/.local_docker
```
Application Log files will be remapped to:
```bash
/storage/logs
```

Don't forget to update your `/etc/hosts` file to include references to your hostname you wish to use for local development - ie I currently use:
```bash
127.0.0.1 local.{applicationName}.{tld}           // reference to the application instance (php/nginx)
127.0.0.1 local.{applicationName}.mysql           // reference to the mysql instance
```
## Summary

**VERY MUCH A WORK IN PROGRESS**

Please feel free to provide feedback and guidance if you see anything that can be improved. Feel free to fork if you see any value!

