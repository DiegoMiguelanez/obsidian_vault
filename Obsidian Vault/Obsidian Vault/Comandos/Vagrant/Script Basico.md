Ejecuta un Ubuntu y un Almalinux, les instala Docker, ejecutan un contenedor nginx y cambian el index.html para que se distingan las caracteristicas de cada maquina:

```
Vagrant.configure("2") do |config|
  config.vm.define "ubuntu_vm" do |ubuntu|
    ubuntu.vm.box = "generic/ubuntu2004"
    ubuntu.vm.network "private_network", ip: "192.168.60.10"
    ubuntu.vm.hostname = "ubuntu-vm"

    # Añade un script de aprovisionamiento específico para Ubuntu
    ubuntu.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y docker.io

      # Inicia un contenedor de nginx con un mensaje personalizado
      docker run -d -p 9092:80 --name nginx nginx:latest bash -c "echo 'Bona tarda des un Ubuntu' > /usr/share/nginx/html/index.html && nginx -g 'daemon off;'"
    SHELL
  end

  config.vm.define "almalinux_vm" do |centos|
    centos.vm.box = "almalinux/8"
    centos.vm.network "private_network", ip: "192.168.60.11"
    centos.vm.hostname = "almalinux-vm"

    # Añade un script de aprovisionamiento específico para CentOS
    centos.vm.provision "shell", inline: <<-SHELL
      sudo yum install -y docker
      sudo systemctl start docker
      sudo systemctl enable docker
      sudo usermod -aG docker vagrant

      # Inicia un contenedor de nginx con un mensaje personalizado
      docker run -d -p 9093:80 --name nginx nginx:latest bash -c "echo 'Bona nit des Almalinux' > /usr/share/nginx/html/index.html && nginx -g 'daemon off;'"
    SHELL
  end

  
  
end
```