# ansible
inventory.yaml - example 
```yml
all: # Parent group
  vars:
    ansible_user: ansible # The username to use when connecting to the host
    ansible_ssh_private_key_file: /home/user/.ssh/ansible # Private key file used by SSH. Useful if using multiple keys and you do not want to use SSH agent.
  children:
    masters: # Child group
      hosts:
        kube-m01: # Hostname
          ansible_host: 111.222.333.444 # Host IP or FQDN
    workers:
      hosts:
        kube-w01: 
          ansible_host: 111.222.333.444
        kube-w02: 
          ansible_host: 111.222.333.444
```