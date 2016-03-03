# defining constant variables to be used later
VAGRANT_API_VERSION = "2"


# Specify which version of Vagrant API to use 
Vagrant.configure(VAGRANT_API_VERSION) do |config|


	#specifying the base box 
	# if it is hosted on vagrant cloud specify only the name
	config.vm.box = "ubuntu/trusty64"


	# specify the network configurations
	# the below line service listening on port 80 of guest machine can be accessed
	# from the host machine on port 8931
	# the auto_correct option tells Vagrant to resolve port collisions automatically
	config.vm.network :forwarded_port, guest: 80, host: 9898, auto_correct: true

	# specify VM provider like virtualbox 
	# id variable is VM's ID which vagrant passes 
	config.vm.provider "virtualbox" do |v|
		v.name = "Test Vagrant"
		v.customize ["modifyvm", :id, "--memory", "2048"]
	end

	# provisoning with Shell script
	# specify the provisioning type - shell
	config.vm.provision "shell" do |s|
		s.path = "provision/setup.sh"
	end

end
	
	



