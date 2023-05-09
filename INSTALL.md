# INSTALL
## _install procedure_

the program was tested only on a RedHat 8 server.

## Requirements
###  additional rpms required on RH8
  
- python39-devel
- libcurl-devel-7.61.1-25.el8_7.3 
- openssl-devel

for install the required rpms run the follow command
``dnf install -f libcurl-devel-7.61.1-25.el8_7.3 python39-devel openssl-devel``

### additional python modules required on RH8
on RH8 are required the followings python3 modules

- argparse
- termcolor 
- os
- requests
- urllib3
- jq

for install the required modules run the follow command
``pip3 install  argparse termcolor  os requests urllib3 jq``

Please consider using VENV pythons to be sure not to create conflicts with the packages installed on the operating system


copy the file in you preferred location and make it executable

``chmod 750 aah-manage``

