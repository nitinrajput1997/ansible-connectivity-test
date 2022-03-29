# ansible-connectivity-test

In this scenario, we have two server say ansible-controller-host and target-host. So in this, we will test ansible connectivity between ansiible-controller-host and target-host.

### Install Ansible on controller host
```bash
$ sudo apt update
$ sudo apt install software-properties-common
$ sudo add-apt-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible
$ ansible --version
```

### SSH into target-host from controller-host
```bash
$ ssh tagethost@ip
$ exit
```
### Create inventory.txt file
```bash
$ mkdir test-proj
$ cd test-proj
$ sudo vi inventory.txt
  # add this to inventory.txt file
  target-host-name ansible_host=target-host-ip ansible_ssh_pass=target-host-password
```

### Run the test
```bash
$ ansible target-host-name -m ping -i inventory.txt
```
