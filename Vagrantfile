# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

Vagrant.configure("2") do |config|

  config.vm.box = "centos/7"

  config.vm.provider "virtualbox" do |v|
    v.cpus = 2
    v.memory = 2048
  end

  config.vm.define :kubemaster do |kbm|
    kbm.vm.hostname = "kubemaster.hdp.com"
    kbm.vm.network :private_network, ip: "172.16.0.21"
    kbm.vm.provision :ansible do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "provisioning/provision.yml"
      ansible.limit = 'kubemaster'
    end
  end

  config.vm.define :kubeagent1 do |kba1|
    kba1.vm.hostname = "kubeagent-one.hdp.com"
    kba1.vm.network :private_network, ip: "172.16.0.22"
    kba1.vm.provision :ansible do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "provisioning/provision.yml"
      ansible.limit = 'kubeagent1'
    end
  end

  config.vm.define :kubeagent2 do |kba2|
    kba2.vm.hostname = "kubeagent-two.hdp.com"
    kba2.vm.network :private_network, ip: "172.16.0.23"
    kba2.vm.provision :ansible do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "provisioning/provision.yml"
      ansible.limit = 'kubeagent2'
    end
  end

end
