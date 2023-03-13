# autor: Gilvanildo DevOps
Vagrant.configure("2") do |config|

# Informando ao Vagrant que vamos utilizar uma imagem do Ubuntu
  config.vm.box = "ubuntu/trusty64"

  # configurando a VM de aplicação
  config.vm.define:app do |app_config|
    app_config.vm.network "private_network", ip: "192.168.56.7"
    # Instalando o Puppet na VM (algumas imagens já vem com o Puppet instalado)

    app_config.vm.provision "shell", inline: "sudo apt-get update && sudo apt-get install -y puppet"
    # informando ao Vagrant para prosseguir com o provisionamentoutilizando o Puppet

    app_config.vm.provision "puppet" do |puppet|
      puppet.manifest_file = "app.pp"
    end

    # Utilizando o Virtualbox como provider
    app_config.vm.provider:virtualbox do |v|
      v.name = "Projeto_2"
      v.memory = 1024
      v.cpus = 1
    end
  end
end
