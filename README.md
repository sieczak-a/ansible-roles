### Purpose of repository
Role mywebapp shows how to use molecule testing module from ansible. No more manual creating vm's, ssh to them and finally test configuration. Molecule offers dynamic provisioning of docker containers for testing purposes.

### Environment
It is recommended to create python virtualenv. Using virtualenv you can better manage ansible and other packages versions.

```bash
mkdir python
cd python/
sudo apt install python3-virtualenv
virtualenv molecule
source ~/python/molecule/bin/activate
pip3 install "molecule[lint,ansible,docker]"
alias mol=molecule
molecule init role 'roles.mywebapp' --driver-name=docker
cd mywebapp/
```

### Warning
I have ARM64 architecture so some of the images could not work on your local computer.

### Molecule - usage
```bash
mol create
mol reset
mol destroy
mol verify
mol converge
mol list
molecule login -h ubuntu
molecule login -h centos

```
