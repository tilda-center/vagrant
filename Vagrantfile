# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.define "meka" do |meka|
        meka.vm.box = "hfm4/centos7"
        meka.vm.network :private_network, ip: "192.168.33.33"
        meka.vm.provision :ansible do |ansible|
            ansible.playbook = "provision/site.yml"
            ansible.host_key_checking = false
            ansible.groups = {
                "vagrant" => ["meka"],
            }
        end
    end
end
