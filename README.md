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


### Ping

    ansible -i hosts_ci2.yml executors -m ping

### Reboot all test executors

    ansible -i hosts_ci2.yml test-executors -a 'reboot'


### APT upgrade

    ansible -i hosts_ci2.yml test-executors -a 'apt -y full-upgrade'

####

    ansible-playbook ../../cider-ci_v5/deploy/executors-deploy_play.yml -i hosts_ci2.yml -l ci-g2018-07
