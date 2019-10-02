# Vagrant JVM Apps Development

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](/LICENSE)

This is my standard Vagrant VM for ease the provision of server side __JVM based application__ development
environment.


## Stacks

- Vagrant box base: [ubuntu/bionic64](https://app.vagrantup.com/ubuntu/boxes/bionic64) (Ubuntu 18.04LTS)
- Python: Python3 & Pip3
- JDK: OpenJDK 8 (jdk-8u222)
- Postgresql: [10](https://www.postgresql.org/docs/10/index.html)

> _This repository will maintain and update overtime._


### Usage

Copy the `Vagrantfile` and `provision/` folder to wherever your project root directory or as your own customize usage.


### Running

- __Requirement:__
  - [Install VirtualBox](https://www.virtualbox.org/wiki/Downloads), I use VirtualBox 5.2
  - [Install Vagrant](), I use Vagrant 2.2

- __Run and provision Vagrant:__

```bash
# To create, start and provision Vagrant for the first time
vagrant up

# To re-provision Vagrant (need to 'vagrant up' beforehand)
vagrant provision

# To remote (ssh) inside Vagrant
vagrant ssh

# To stop Vagrant
vagrant halt

# To check Vagrant status
vagrant status

# To destroy (remove) Vagrant
vagrant destroy
```

### Provision

- JDK
  - Add `JAVA_HOME` to environment variable.
  - Add `java` & `javac` to path.

- Python3
  - Install `pip3`
  - Access python3 and pip with alias `python, py, pip`

- Postgresql
  - Username: `postgres`, Password: `<empty>`, guest-port: `5432`, host-port: `5433`

Details about provision apps and util can be found in [provision](/provision/playbook.yml) file.

### Customization

- __Hardware specs__

  Vagrant vm specs by default is:
  - CPUs: 2
  - Memory: 2GB
  - Storage: 10GB

  You can customize it by set the environment variable in host OS, as:
  - `VAGRANT_CPUS`, for number of CPUs. eg. `VAGRANT_CPUS=4`
  - `VAGRANT_MEMORY`, for number of memory in MB. eg. `VAGRANT_MEMORY=4096`
  - `VAGRANT_STORAGE`, for number of storage. eg. `VAGRANT_STORAGE=20GB`

  You will need to pre-install Vagrant's disksize plugin in order to ease the storage size customization.
  To install the plugin, run:

  ```bash
  vagrant plugin install vagrant-disksize
  ```

  Destroy and re-up Vagrant if been exists.

### Todos

- [ ] Add GraalVM support?

## License

License under the MIT license. See [LICENSE](/LICENSE) file.
