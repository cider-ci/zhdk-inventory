check:

* 2016-03

ping OK:

* 2016-01
* 2016-02
* 2016-04
* 2016-05
* 2016-06
* 2016-07

* 2018-06
* 2018-07
* 2018-08


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
