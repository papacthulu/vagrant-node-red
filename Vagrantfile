Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "forwarded_port", guest: 1880, host: 8080
  config.ssh.keep_alive = true
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
	curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
	apt-get install -y nodejs
	npm install npm --global
	npm install -g --unsafe-perm node-red node-red-dashboard
  SHELL

  config.vm.synced_folder "node-red/", "/home/node-red"
  config.vm.provision "shell", inline: "node-red --userDir /home/node-red",
    run:"always"

  config.vm.provision "shell", inline: "echo \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*;echo NODE-RED is running;echo \"pkill -f node-red\" to murder node-red the dirty way;echo \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*",
    run:"always"
end