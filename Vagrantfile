Vagrant.configure("2") do |config|
  config.vm.box = "archlinux/archlinux"

  config.vm.provider "virtualbox" do |vb|
    # Add two USB controllers
    vb.customize ["modifyvm", :id, "--usb", "on"]
    vb.customize ['storagectl', :id, '--name', 'USB Controller', '--add', 'usb']
  end
  # We need Python for Ansible
  config.vm.provision "shell",
    inline: "pacman -Q 'python' || pacman -S 'python' --noconfirm"
    
  # And now, we can use the playbook
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "provision.yml"
  end
end