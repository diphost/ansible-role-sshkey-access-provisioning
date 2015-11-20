anlible-role-sshkey-access-provisioning
=======================================

[Ansible](https://github.com/ansible/ansible) role to assemble and deploy authorized_keys according to the host configuration file
The configuration file can be generated from a script https://github.com/diphost/sshkeys-vault-precommit for example

Features
--------

* SSH-algorithms autodiscovery
* Many persons for many users for many hosts
* Multiple ssh keys for any person

Use
---

* Create required directory structure
* ansible-playbook -i hosts playbook.yml

Directory structure
-------------------

```
ansible-role-sshkey-access-provisioning/
\____...                                   # this role
group_vars/
\____ ssh-access-hosts                     # group specific vars (python path, ssh user, ...)
hosts                                      # hosts list
playbook.yml                               # our playbook
```

Host configuration sample
-------------------------

```yml
---
users:
- algs:
  - authorized:
    - ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBIpBgrS6TH7HlF2JvIuWOxpXGizNkotkWyJoKMhv2idZkMXkTapyHQ1hXJf8wepBUTkuu8AV65RjF0AZxspDEho=
      alice@notebook
    name: ecdsa
  - authorized:
    - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAAgQCfx4o/E8Ui4bXRSnjRfzczXe4Uz568O3KDzlAAvlb9Ley2YWD1w5mso+Rekg43+IyLtCAmP6hhzQPR4hmOcxmwuBXOuHgTThy+W14tOlEP+W6qH58td6GzBHM8KbhTKKERUkGz5EDc9LYgxkDecfjvGwL2J/YsOX0KhTNNGjNyAQ==
      alice@notebook
    name: rsa
  user: admin
- algs:
  - authorized:
    - ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBJbD/13MZvVF7eJz5MTSWkQgZT7qDwCy/KkXcO8oU8YxRURnmTp2AqHSRnMsSPwD9ep9ccikZcKVRvUxI2YypSA=
      givi@office
    - ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBBE+A0jwCQoOidiENsbcHsMFpaVbdt5u2FltGPRML4+bKSRKRsA03x2oireON2OG6/De2O1D3EWDFXsUHCAujG8=
      givi@home
    name: ecdsa
  - authorized:
    - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAAgQDLWUErd6Ul2bdC5+4x2P5aqFOli+xKiTBSC1iuHNKIHN+XCzQCxUR8baSweDmTwwhInWJ8SFEPXMcOROBIKrbYS19cvCLGTJ6o9YyOpcv3HtkcgiR+d0Kl8kp3qp7zMDULaSSp8M2QYsVXQtabgx2V13KBfxNqaKIcRGjdbZA+dw==
      givi@office
    - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAAgQCtE9aWuP1FkK5yA3cxDtnoqC+51xuGts5VhKpr/la6Eqg+5WD1rIp6xw9YZfx9eOzpTY6Ac+Z+FobdK2emx1Rnnaj0mEehgEDFfBqon9H22HkiegPsOl4JpuMIc11H54/uOgV1TXLMPYjiRhnTjNZO5wdTsOK5AQKTzlWEfTGNbQ==
      ashot@android
    - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAAgQCh7zFizQu/ApHEPSXDTFaT6yZYGhJL0KLsrK1Qpv4mP3byuXp3Q4Rm3jXhFxSAJSsy77MVlj+SCYGG+bCv9jBBXmGinnl68oH9moUXGYt0cmYppjnPB2dW8k46HWsGYXlkuszfMuEpxXfs3QeK+4nn7HFVR+VLZ2FvRpvtLbeZQw==
      ashot@office
    name: rsa
  user: dev1
```

--
[![LICENSE WTFPL](wtfpl-badge-1.png)](LICENSE)

