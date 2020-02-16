# APX - Dockerized development environment with **A**pache Webserver, **P**HP & **X**debug
This is a Docker-Compose configuration for setting up a fast PHP development environment for everyone.

The configuration creates a relatively simple running PHP versions 7.2, 7.3 & 7.4 environments with its own Apache Web server environment.
An Xdebug environment is also made available for debugging purposes.

The project name APX stands for:
  - **A** = Apache Webserver
  - **P** = PHP versions 7.2, 7.3 & 7.4 at the same time
  - **X** = Xdebug installed, configured and ready to use

# Features

  - Docker environment with simultaneously running PHP versions 7.2, 7.3 & 7.4 at the same time
  - Each PHP version or environment has its own Apache web server environment. This means that the web server can be  configured individually for each PHP version.
  - An installed and configured Xdebug environment is available for all available PHP versions. This can be addressed and used under the standard port 9000.

### Installation
APX requires Docker v19+ and docker-compose v1.25+ to run.

Create and start the APX containers.
```sh
$ docker-compose up
```

That's it...
To check this installation, start a web browser and open the addresses:
 - http://localhost:872/phpinfo.php or http://127.0.0.1:872/phpinfo.php => This is the address for the PHP 7.2 docker environment
 - http://localhost:873/phpinfo.php or http://127.0.0.1:873/phpinfo.php => This is the address for the PHP 7.3 docker environment
 - http://localhost:874/phpinfo.php or http://127.0.0.1:874/phpinfo.php => This is the address for the PHP 7.4 docker environment

If the installation is successful, you should see a PHP info page for each environment.


### How to use the different environments?
The structure of the APX project is structured as follows:
```sh
APX/
├── docker-compose.yml
├── Infrastracture
│   ├── Php72-Apache
│   │   └── Dockerfile
│   ├── Php73-Apache
│   │   └── Dockerfile
│   └── Php74-Apache
│       └── Dockerfile
├── Logs
│   ├── Php72-Apache
│   ├── Php73-Apache
│   └── Php74-Apache
├── README.md
└── Resources
    ├── Php72-Apache
    │   └── phpinfo.php
    ├── Php73-Apache
    │   └── phpinfo.php
    └── Php74-Apache
        └── phpinfo.php
```
# Explanation of the individual project folders
- **Infrastructure** -> Here are the Dockerfiles and Docker definitions for each environment located.
- **Logs** -> Here are the Apache Webserver logs for each environment located. You can easily access the apache webserver logs files for each Apache / PHP environment
- **Resources** -> This folder contains the static files and content from the developer.
There is a separate Document Root / Document folder for each Apache / PHP environment. If a PHP file is to be executed under PHP version 7.2, it is sufficient to save this file in the folder APX/Resources/Php72-Apache. The file can then be called up relatively easily at the localhost address with port 872 of the machine. The same applies to the other PHP versions and environments. Depending on the PHP version or environment, the specification of the IP port number is very important. For PHP 7.3 it is the IP port number 873 and for PHP 7.4 it is the IP port number 874.

### Start / Stop the Environment
The environment can be started easily with the following command:
```sh
$ docker-compose start
```
The following command is sufficient to stop or end the environment:
```sh
$ docker-compose stop
```

### Liability / Important declaration on the project
Use of this project is entirely at your own risk. No guarantee, warranty or liability is assumed by the creator of this project. The environment should only run on a test environment. Use in a productive environment should not take place. The project is a leisure project.

License
----

MIT
