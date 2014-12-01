## Vagrantfile

```Ruby
# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

    config.vm.provider "docker" do |d|
        d.build_dir = "./"
        d.has_ssh = true
        d.ports = ["8090:80"]
        d.build_args = ["-t=ohitu:v1"] # args passed to docker build. -t imageName:imageTag | imageName
        d.name = "ohitu" # container name
        d.create_args = ["-h", "ohitu"] # args passed to docker run

    end

    config.ssh.port = 22
    config.ssh.username  = "vagrant"
    config.ssh.password = "vagrant"

  config.vm.synced_folder "./", "/vagrant"
  config.vm.synced_folder "/opt/klear-development/", "/opt/klear-development"

  config.vm.provision "ansible" do |ansible|
     ansible.playbook = "Provision/playbook.yml"
     ansible.tags = ENV['ANSIBLE_TAGS']
     ansible.verbose = "vvvv"
  end

end

```

http://docs.vagrantup.com/v2/docker/configuration.html
