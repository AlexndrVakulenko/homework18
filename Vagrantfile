Vagrant.configure(2) do |config|

config.vm.define "backup" do |vm1|
	vm1.vm.box = "bento/ubuntu-22.04"
	vm1.vm.hostname="backup"
	vm1.vm.network :private_network, ip: "192.168.56.160"
	vm1.vm.provider "virtualbox" do |vb|
		vb.memory = "1024"
		vb.cpus = "1"
		needsController = false
		unless File.exist?('./backup/sata1.vdi')
        vb.customize ['createhd', '--filename', './backup/sata1.vdi', '--variant', 'Fixed', '--size', 2048]
        needsController =  true
		end
        if needsController == true
           vb.customize ["storagectl", :id, "--name", "SATA", "--add", "sata" ]
           vb.customize ['storageattach', :id,  '--storagectl', 'SATA', '--port', 1, '--device', 0, '--type', 'hdd', '--medium', './backup/sata1.vdi']
        end
	end
end


config.vm.define "client" do |vm2|
	vm2.vm.box = "bento/ubuntu-22.04"
	vm2.vm.hostname="client"
	vm2.vm.network :private_network, ip: "192.168.56.150"
	vm2.vm.provider "virtualbox" do |vb|
		vb.memory = "1024"
		vb.cpus = "1"
	end
end

end
