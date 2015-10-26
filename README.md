anlible-role-sshkey-access-provisioning
=======================================

[Ansible](https://github.com/ansible/ansible) role to assemble and deploy authorized_keys according to the host configuration file

Features
--------

* SSH-algorithms autodiscovery
* Many persons for many users for many hosts
* Multiple ssh keys for any person

Host configuration sample
-------------------------

```yml
---
users:
- algs:
  - authorized:
    - ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEAuCZ1ovq6lUwc9me1ENX/Jw7VrDbpIJt8h0c7K25puFLPI9d45HyQNbHYaxy4Arl3yft5JjnOqm8ERDs9Gy0H8RGBBX1/+EhnM/SFyJ7J9+qF0EAgGGF7ID6XDXyXQxilYn6R7mDz02ZCuQtLFY9VGF5lfWKWR10soId+FdIW9prEVHHWSHZnXuc90z0PFarFD4m9vbgK534X/oEDuc2tIkUvOeZomcJaJ/3oVMP4IFpqbTBnf1BuCc1QvywPcjzOCxqkon05Vf5Xi5gfPFJRTkO+CyfqkcACevTuqNWix6623Nte605pNMXmeEoiUcBbI4n5HjUz2x11yGZq2hy6zp==
      alice@home
    - ssh-rsa AAAAB3NzaC1yc2EAATTBIwAAAQEAuCZ1ovq6lUwc9me1ENX/JrWVrDbpIJX8h0c7K25puFLPI9d45HyQNbHYaxy4Arl3yft5JjnOqm8ERDs9Gy0H8RGBBX1/+EhnM/SFyJ7J9+qF0EAgGGF7ID6XDXyXQxilYn6R7mDz02ZCuQtLFY9VGF5lfWKWR10soId+FdIW9prEVHHWSHZnXuc90z0PFarFD4m9vbgK534X/oEDuc2tIkUvOeZomcJaJ/3oVMP4IFpqbTBnf1BuCc1QvywPcjzOCxqkon05Vf5Xi5gfPFJRTkO+CyfqkcACevTuqNWix6623Nte605pNMXmeEoiUcBbI4n5HjUz2x11yGZq2hytEQ==
      givi@home
    name: rsa
  user: admin
```


--
[![LICENSE WTFPL](wtfpl-badge-1.png)](LICENSE)

