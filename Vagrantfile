# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.define "tilda" do |tilda|
        tilda.vm.box = "debian-jessie"
        tilda.vm.box_url = "https://ftp.lugons.org/vagrant/debian-8.0-x86_64.box"
        tilda.vm.network :private_network, ip: "192.168.33.33"
        tilda.vm.provision :ansible do |ansible|
            ansible.playbook = "provision/site.yml"
            ansible.host_key_checking = false
            ansible.groups = {
                "vagrant" => ["tilda"],
            }
        end
    end
end
