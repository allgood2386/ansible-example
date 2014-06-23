#Dependencies
https://galaxy.ansible.com/list#/roles/932
https://galaxy.ansible.com/list#/roles/434

##Install dependencies
```$ ansible-galaxy install geerlingguy.php-mysql```

```$ ansible-galaxy install geerlingguy.drupal```

So that last dependency is kinda up in the air atm depending on when we can get
upstream changes in that I made. For now, there is a submodule that will
will get cloned in if you use the --recursive option, later on we can
just install the role.

##Step-by-step (and things to know)
1. Install Virtualbox https://www.virtualbox.org/wiki/Downloads
2. Install Vagrant http://www.vagrantup.com/
3. ```vagrant box add p2 http://puppet-vagrant-boxes.puppetlabs.com/ubuntu-server-12042-x64-vbox4210.box```
4. ```git clone --recursive git@bitbucket.org:taoticreative/ansible-template.git {projectpath}```
5. Copy ./Vagrantfile.example -> ./Vagrantfile
6. Edit ip settings in ./Vagrantfile
7. Create a vars/drupal.yml file, edit accordingly for your repos.
8. A db can be loaded into the vm by placing a db dump in ./data directory (this will be done automatically if you provision first).
9. data from the host os {projectpath}/data/yourdbfile.sql will be in the vmbox at /vagrant/data/yourdbfile.sql
10. ./www (in the host) is shared with /var/www/yourprojectpath (which is defined in vars/drupal.yml)(this is how you edit locally).
11. Once your project settings are set from the root (Vagrantfile will be in pwd) type vagrant up. This will create your vm.
12. To reprovision (careful this will wipe your db at the momment) type vagrant provision (this will redo all your ansible tasks).
To reload type vagrant reload, this will restart the vm and give you a new ip/shared data path if you need.
