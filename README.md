# Vagrant JVM Apps Development

This is my standard Vagrant VM for ease the provision of server side __JVM based application__ development
environment.


## Stacks

- Vagrant box base: [ubuntu/bionic64](https://app.vagrantup.com/ubuntu/boxes/bionic64) (Ubuntu 18.04LTS)
- Python: Python3 & Pip3
- JDK: OpenJDK 8 (jdk-8u222)
- Postgresql:
- MongoDB:

> _This repository will maintain and update overtime._

## TL;DR

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

  You may need to pre-install Vagrant's disksize plugin in order to ease storage customization.

  ```bash
  vagrant plugin install vagrant-disksize
  ```

### Todos

- [x] OpenJDK 8 and `JAVA_HOME` env vars.
- [x] Python3 & pip3 support.
- [ ] Postgresql 10 and Postgresql-Client, with Connection string as env vars.
- [ ] MongoDB 4, with Connection string as env vars.


## License

License under the MIT license. See [LICENSE](/LICENSE) file.
