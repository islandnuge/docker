# frontalnugity/docker

## Overview

My attempt at creating a standard, generic docker configuration which is to be used in each web application we develop.

Still very  much learning Docker and its dependencies, please feel free to provide feedback and guidance if you see anything that can be improved.

Feel free to fork if you see any value!

## Loadout:

Intended as a clean setup for typical laravel/php development:

- Nginx
- MySQL
- PHP 7.

## Installation / Usage

For each web project clone it into your project as `/docker` and modify the configuration files per your preference.

Setup assumes that your working directory for your web-app will be:

`/application`

and that persistent data will be created/stored in:

`/storage/db`

Log files will be remapped to:

`/storage/logs`

* VERY MUCH A WORK IN PROGRESS *



