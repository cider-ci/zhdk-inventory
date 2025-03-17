ZHdK Cider-CI Inventory
=======================

Examples
--------


### Setup remote authorized ssh key

    ssh-copy-id root@REMOTE_HOST


### Ping

    ansible -i hosts_ci2.yml executors -m ping

### Reboot all test executors

    ansible -i hosts_ci2.yml test-executors -a 'reboot'


### APT upgrade

    ansible -i hosts_ci2.yml test-executors -a 'apt -y full-upgrade'

### Install

    ./bin/executors-deploy -l executors-ax101
    ./bin/executors-deploy -l 'ci-executor.madek'

### Traits


    ./bin/executors-traits -l executors-ax101
    ./bin/executors-traits -l ci-ax101-01 -t ci_executor_trait_lxd


#### Reinstall Trait example

clean docker completely, reboot (cleans tmp cache), and then reinstall the trait:

    ./bin/ansible executors-ax101 -i hosts_ci2.yml -m ansible.builtin.shell -a 'apt purge docker-ce docker-ce-cli docker-ce-rootless-extras docker-compose-plugin docker -y && rm -rf /var/lib/docker && reboot'
    ./bin/executors-traits -l executors-ax101 -t ci_executor_trait_docker



###

 CPU1: AMD Ryzen 9 5950X 16-Core Processor (Cores 32)
   Memory:  128755 MB
   Disk /dev/nvme0n1: 3840 GB (=> 3576 GiB) doesn't contain a valid partition table
   Disk /dev/nvme1n1: 3840 GB (=> 3576 GiB) doesn't contain a valid partition table
   Total capacity 7153 GiB with 2 Disks

Network data:
   eth0  LINK: yes
         MAC:  a8:a1:59:c1:44:b6
         IP:   65.109.69.181
         IPv6: 2a01:4f9:5a:4620::2/64
         Intel(R) Gigabit Ethernet Network Driver
