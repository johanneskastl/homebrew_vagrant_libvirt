Vagrant.configure("2") do |config|

  # name the VMs
  config.vm.define "homebrew" do |node|

    # which image to use
    node.vm.box = "opensuse/Leap-15.5.x86_64"

    # disable synced folders
    node.vm.synced_folder ".", "/vagrant", disabled: true

    # sizing of the VMs
    node.vm.provider "libvirt" do |lv|
      lv.random_hostname = false
      lv.memory = 2048
      lv.cpus = 2
    end

    # set the hostname
    node.vm.hostname = "homebrew"

    node.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "ansible/playbook-vagrant.yml"
    end # node.vm.provision

  end # config.vm.define nodes
end
