Vagrant.configure(2) do |config|

	config.vm.define "vagrant" do |vagrant|
		vagrant.vm.box = "bento/ubuntu-16.04"
		vagrant.vm.hostname = "vagrant.loc"
		vagrant.vm.network :private_network, ip: "192.168.100.10"

		import.vm.provision :ansible do |ansible|
			ansible.playbook = "dev/provisioning/playbook.yml"
		end
	end

	config.vm.synced_folder ".", "/vagrant"

	config.vm.provider "virtualbox" do |v|
		v.memory = 2048
		v.cpus = 2
	end
end
