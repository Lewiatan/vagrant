Vagrant.configure(2) do |config|

	config.vm.define "import" do |import|
		import.vm.box = "bento/ubuntu-16.04"
		import.vm.hostname = "import.dev"
		import.vm.network :private_network, ip: "192.168.100.10"

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
