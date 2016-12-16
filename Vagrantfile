servers=[
  {
    :hostname => "test-media",
    :ip => "192.168.50.2",
    :box => "v0rtex/xenial64",
    :ram => 512,
    :cpu => 1
  }
]

Vagrant.configure(2) do |config|
    servers.each do |machine|
        config.vm.define machine[:hostname] do |node|
            node.vm.box = machine[:box]
            node.vm.hostname = machine[:hostname]
            node.vm.network "private_network", ip: machine[:ip]
            node.vm.provider "virtualbox" do |vb|
                vb.customize ["modifyvm", :id, "--memory", machine[:ram]]
	    end
	end
    end
end
