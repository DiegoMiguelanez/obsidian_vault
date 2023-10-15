**Vagrant**

**Componentes Básicos:**

- **Box:** Imagen base de una máquina virtual.
- **Vagrantfile:** Archivo de configuración en Ruby que define la VM.

**Comandos Básicos:**

- `vagrant init [nombre del box]`: Inicia un nuevo proyecto Vagrant.
- `vagrant up`: Crea y arranca la VM.
- `vagrant ssh`: Inicia sesión en la VM por SSH.
- `vagrant halt`: Detiene la VM.
- `vagrant destroy`: Elimina la VM.
- `vagrant suspend`: Pausa la VM.
- `vagrant resume`: Reanuda la VM desde la pausa.
- `vagrant status`: Para ver el estado de la maquina creadas

**Ejemplo de Vagrantfile:**

```
Vagrant.configure("2") do |config| 
	config.vm.box = "bento/ubuntu-20.04"
	config.vm.network "private_network", ip: "192.168.33.10" 
end
```

**Plugins Útiles:**

- `vagrant-vbguest`: Mantiene actualizados los Guest Additions.
- `vagrant-hostsupdater`: Actualiza automáticamente el archivo hosts.

---

Scripting [https://developer.hashicorp.com/vagrant/docs/provisioning/shell]

```
$script = <<-SCRIPT
echo I am provisioning...
date > /etc/vagrant_provisioned_at
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.provision "shell", inline: $script
end

```