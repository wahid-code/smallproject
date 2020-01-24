servers=[

  {
    :hostname => "server1",
    :ip => "192.168.4.4",
    :box => "ubuntu/bionic64",
    :ram => 1024,
    :cpu => 2,
  }
]
Vagrant.configure(2) do |config|
  servers.each do |machine|
    config.vm.define machine[:hostname] do |node|
      node.vm.box = machine[:box]
      node.vm.hostname = machine[:hostname]
      node.vm.network "private_network", ip:machine[:ip]
      node.vm.provider "virtualbox" do |vb|
        vb.customize ["modifyvm", :id, "--memory", machine[:ram]]
        end
    end
  end 
end   
