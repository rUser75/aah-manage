# aah-manage.py - Ansible Automation Hub Management Script
## Overview

aah-manage.py is a command-line tool designed to facilitate the management of various resources within Ansible Automation Hub. This script enables users to perform operations such as listing, synchronizing, and managing Execution Environments (EE) and Ansible collections. It is an essential tool for administrators looking to efficiently manage their Ansible Automation Hub instances.

## Features
**List Execution Environments**: Retrieve and display a list of available Execution Environments.
**Synchronize Repositories**: Initiate synchronization of remote repositories to ensure they are up-to-date.
**Manage Collections**: List, remove, or delete Ansible collections from repositories or the system.
**Generate Authentication Tokens**: Create new API tokens for authentication.
**List Available Resources**: Display all available repositories and collections with their descriptions and versions.

## Prerequisites
Python 3.9 or later
Required Python packages: requests, termcolor, jq, urllib3

## Installation
<code style="color : red">text</code>
 You can generate a new AUTHTOKEN using the opion --generateAuthToken you must provvide user and password for the API login. The AUTHTOKEN can be obtained via the http cli:

collections -> API token management

Please note, as wrote in UI WARNING loading a new token will delete your old token.

If you have already configured the API TOKEN please don't generate a new one if you don't know what you're doing

### Clone the Repository:
```sh
git clone <repository-url>
cd <repository-directory>
```

### Install Dependencies:
```sh
pip install requests termcolor jq urllib3
```

### Set Environment Variables (optional):

* AUTH_TOKEN: Your API authentication token.
* AAH_SERVER: The server address for Ansible Automation Hub.

## Usage
### Basic Commands

* List Execution Environments:
```sh
python aah-manage.py --getEEList
```

* Synchronize a Remote Repository:
```sh
python aah-manage.py --sync <community|rh-certified>
```

* List Available Repositories and Collections:
```sh
python aah-manage.py --listAvailables
```

* Generate a New Auth Token:
```sh
python aah-manage.py --generateAuthToken <user:password>
```

### Collection Management

* List Collections:
```sh
python aah-manage.py --getCollectionList --namespace <namespace> --collection <collection_name> --repositoryName <repository_name>
```

* Remove a Collection from Repository:
```sh
python aah-manage.py --removeCollection --namespace <namespace> --collection <collection_name> --repositoryName <repository_name>
```

* Delete a Collection from System:
```sh
python aah-manage.py --deleteCollection --namespace <namespace> --collection <collection_name> --repositoryName <repository_name>
```

### Authentication

* Using Command-Line Argument:
```sh
python aah-manage.py --authToken <TOKEN>
```

* Using Environment Variable: Ensure AUTH_TOKEN is set in your environment.

### Options
* --authToken <TOKEN>: API token for authentication.
* --generateAuthToken <user:password>: Generate a new authentication token.
* --getEEList: List available Execution Environments.
* --getEEVersion: List versions of available Execution Environments.
* --listAvailables: List all available repositories and collections.
* --deleteEE <EEname> <SHA>: Delete the specified Execution Environment image.
* --getCollectionList: List collections in a specified namespace and repository.
* --removeCollection: Remove a specified collection from a repository.
* --deleteCollection: Delete a specified collection from the system.
* --namespace <namespace>: Specify the namespace for collection management.
* --collection <collection_name>: Specify the collection name for management.
* --repositoryName <repository_name>: Specify the repository name for management.
* --sync <REPOREMOTENAME>: Synchronize a remote repository.
* -k: Allow insecure server connections when using SSL.
* -v: Enable verbose output for debugging.

## Notes
* Ensure that the AAH_SERVER environment variable is set to the correct server address.
* The script requires appropriate permissions to perform operations on Ansible Automation Hub.

* the script refers to community|rh-certified may change from installation to installation

## Troubleshooting
Authentication Errors: Verify that the API token is correct and has not expired.
Connection Issues: Ensure the server address is reachable and correct.
Missing Dependencies: Install required Python packages using pip.
