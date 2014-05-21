# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Configuramos la caja que se usará en las maquinas definidas en este VagrantFile. No especificamos URL puesto que la caja se encuentra en VagrantCloud disponible para descarga.
  config.vm.box = "ubuntu/trusty64"
 
#ansible.groups = {
#	"web" => ["web"],
#	"dns" => ["dns"],
#}

# Definimos la máquina web
config.vm.define "web" do |web|
	# Configuramos el nombre de la máquina
  config.vm.hostname = "web"
  # Configuramos una red privada, que permitirá la conexión entre las máquinas de esta misma red además de con el anfitrión.
	config.vm.network "private_network", ip: "192.168.50.80"

end

#config.vm.define "dns" do |dns|
#	config.vm.hostname = "dns"
#	config.vm.network "private_network", ip: "192.168.50.53"
#end

# Indicamos que el aprovisionamiento se realize con Ansible
config.vm.provision "ansible" do |ansible|
  # Indicamos el Playbook de ansible a usar
	ansible.playbook = "provisioning/playbook.yml"
end

end
