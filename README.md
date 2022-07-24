# Caravel User Project

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) [![UPRJ_CI](https://github.com/efabless/caravel_project_example/actions/workflows/user_project_ci.yml/badge.svg)](https://github.com/efabless/caravel_project_example/actions/workflows/user_project_ci.yml) [![Caravel Build](https://github.com/efabless/caravel_project_example/actions/workflows/caravel_build.yml/badge.svg)](https://github.com/efabless/caravel_project_example/actions/workflows/caravel_build.yml)

---
## Requirements
- Docker 
- Python3 with PIP
- Volare
##### Docker

Uninstall older versions of docker just in case :
```
$ sudo apt-get remove docker docker-engine docker.io containerd runc
```
Then you need to install packages to allow apt to use a repository over HTTPS :
```
$ sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```
Add Docker’s official GPG key:
```
$ sudo mkdir -p /etc/apt/keyrings
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```
Use the following command to set up the repository:
```
  $ echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
Install the latest version of Docker Engine:
```
$ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```
 Verify that Docker Engine is installed correctly by running the hello-world image. 
```
$ sudo docker run hello-world
```
##### PIP for Python 3.6+
Install python3 and PIP for python3 
```
$ sudo apt install python3
$ sudo apt install python3-pip
```
Verify that Python3 and Python3-pip installed correctly by running following commands
```
$ python3 --version
$ pip --version
```
##### Volare 
[Volare](https://github.com/efabless/volare) is necessary for skywater pdks. 
```
$ sudo python3 -m pip install --upgrade --no-cache-dir volare
```
---
### Setup 

Create an empty Git project on Github. It must be public repository. 

Create an empty folder and navigate to it.
```
$ mkdir -p <folder_name> 
$ cd <folder_name> 
```
Clone cravel_user_project and setup the git environments as [caravel_user_project quick start](docs/source/quickstart.rst) document says. 
```
# Clone caravel_user_project and navigate it.  
$ git clone -b mpw-6c https://github.com/efabless/caravel_user_project <your_github_repo_name>
$ cd <your_github_repo_name>

$ git remote add origin <your_github_repo_URL>

# Create a new branch, name it anything you want. 
$ git checkout -b <my_branch>

# This push will require username and password for your github account. You should enter token instead of password.
$ git push -u origin <my_branch>
```
Setup your local environments.
```
$ export OPENLANE_ROOT=~/<directory_name>/openlane 

$ export PDK_ROOT=~/<directory_name>/pdks

# Before you setup 
$ sudo chmod 777 /var/run/docker.sock

# Ready to go
$ make setup
```
## Please fill in your project documentation in this README.md file 

Refer to [README](docs/source/quickstart.rst) for a quick start of how to use caravel_user_project

Refer to [README](docs/source/index.rst) for this sample project documentation. 
