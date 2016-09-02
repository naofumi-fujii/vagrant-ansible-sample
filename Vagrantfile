# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure('2') do |config|
  config.vm.box      = 'ubuntu/wily64'
  # config.vm.hostname = 'rails-dev-box'

  # config.vm.network :forwarded_port, guest: 3000, host: 3000
  config.vm.provision :shell, inline: "sudo apt-get -y install libffi-dev libssl-dev"

  config.vm.provision :guest_ansible do |guest_ansible|
    guest_ansible.playbook = "playbook.yml"
    # guest_ansible.extra_vars = extra_vars
    guest_ansible.sudo = false
  end
  config.vm.provision :shell, inline: "ansible-galaxy install sansible.ruby"

  config.vm.provider 'virtualbox' do |v|
    v.memory = 1024
    v.cpus = 2
  end
end
