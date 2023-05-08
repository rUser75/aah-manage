# README

## Description

This is a cli simple interface to the Ansible Automation Hub that use the AAH API to perform some actions. 

The action formormed are:
- Repo Management sync the remote repo community and th-certified
- List the availables Execution Environments images (todo)
- Delete Execution Environments images (todo)

## Basic Usage
### Installation
see INSTALL.md file

### Synopsis
aah-manage commands follow a simple format:
````
./aah-manage -h
usage: aah-manage [-h] --authToken AUTHTOKEN [-k] [-v] [--sync REPOREMOTENAME]

optional arguments:
  -h, --help            show this help message and exit
  --authToken AUTHTOKEN
                        API token for authentication
  -k                    Allow insecure server connections when using SSL
  -v                    write verbose output
  --sync REPOREMOTENAME
                        start sync of remote repository (Repo Managment)
````

You can retrieve the AUTHTOKEN using the opion **--retriveAuthToken** you must provvide user and password for the API login.
The AUTHTOKEN can be obtained via the http cli:

*collections -> API token management*

Please note, as wrote in UI **WARNING loading a new token will delete your old token.**

If you have already configured the API TOKEN please don't generate a new one if you don't know what you're doing

Before start you must export the enviroment variable **AAH_SERVER** with the FQDN of the Automantion Hub server

``export AAH_SERVER=aahserver.domain``





**This software is provided 'as-is', without any express or implied warranty. In no event will the authors be held liable for any damages arising from the use of this software.**


### External resources

https://access.redhat.com/solutions/6991487
