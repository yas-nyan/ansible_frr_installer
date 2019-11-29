# ansible FRR installer 

## requirements
- ansible: 2.7~
- debian/ubuntu 

## set varialbles

### frr
```group_vars/frr_hosts.yml
frr_daemons:
  bgpd: true
  isisd: false
  ldpd: false
  nhrpd: false
  ospf6d: true
  ospfd: true
  pimd: false
  ripd: false
  ripngd: false
  zebra: true

FRRVER: frr-7
```

[valid `FRRVER` list](https://deb.frrouting.org/https://deb.frrouting.org/)
 


### credential
group_vars/all/credential.yml
```
ansible_user: ubuntu
ansible_become_pass: VerySecurePassword
```
### hosts
```
[frr_hosts]

frr_tester  ansible_host=192.0.2.1
```

## deploy
```
ansible-playbook -i hosts frr_hosts.yml
```



# license
MIT