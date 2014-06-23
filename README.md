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
