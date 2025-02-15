# README

## Description

This is a simple CLI interface to the Ansible Automation Hub that use the AAH API to perform some actions. 

## Basic Usage
### Installation
see INSTALL.md file


### Synopsis
aah-manage commands follow a simple format:
```
usage: aah-manage [-h] [--authToken AUTHTOKEN | --generateAuthToken CREDENTIAL] [--getEEList] [--getEEVersion] [--listAvailables] [--deleteEE EEname SHA] [--getCollectionList] [--removeCollection]
                  [--deleteCollection] [--namespace NAMESPACE] [--collection COLLECTION] [--repositoryName REPOSITORYNAME] [--force] [--sync REPOREMOTENAME] [--reclaimSpace] [-k] [-v]

optional arguments:
  -h, --help            show this help message and exit
  --authToken AUTHTOKEN
                        API token for authentication
  --generateAuthToken CREDENTIAL
                        generate a NEW AuthToken. You must specify the credetial for the login (user:password). WARNING: loading a new token will delete your old token
  --getEEList           print the list of available EE images
  --getEEVersion        print the list of available EE images version
  --listAvailables      list all available repositories and collections
  --deleteEE EEname SHA
                        delete the specified EE image
  --getCollectionList   print the list of community general, experimental
  --removeCollection    remove the specified collection from repository
  --deleteCollection    remove the specified collection from system
  --namespace NAMESPACE
                        Namespace for the collection, required with --getCollectionList, --removeCollection, and --deleteCollection
  --collection COLLECTION
                        Name of the collection,required with --getCollectionList, --removeCollection, and --deleteCollection
  --repositoryName REPOSITORYNAME
                        Name of the repository, required with --getCollectionList, --removeCollection, and --deleteCollection
  --force               force the operation without asking for confirmation
  --sync REPOREMOTENAME
                        start sync of remote repository (Repo Managment). REPOREMOTENAME: community / rh-certified
  --reclaimSpace        Trigger an asynchronous space reclaim operation.
  -k                    Allow insecure server connections when using SSL
  -v                    write verbose output

```


# italiano

README [![it](https://img.shields.io/badge/lang-it-green.svg)](https://github.com/rUser75/aah-manage/blob/main/README-ita.md)

------
# English

README [![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/rUser75/aah-manage/blob/main/README-en.md)


**This software is provided 'as-is', without any express or implied warranty. In no event will the authors be held liable for any damages arising from the use of this software.**


### External resources

https://access.redhat.com/solutions/6991487
