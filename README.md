# vagrant-node-red
Dead simple node-red with Vagrant!

[Download Git](https://git-scm.com/downloads)  
[Download Vagrant](https://www.vagrantup.com/)
  
```sh
$ git clone https://github.com/papacthulu/vagrant-node-red.git
$ cd vagrant-node-red
$ vagrant up
```

That's it! Navigate to localhost:8080

node red is now running in a detached screen called node-red

## Problems?

Can't stop it?
```sh
vagrant ssh
sudo pkill -f node-red
exit
vagrant halt
```
