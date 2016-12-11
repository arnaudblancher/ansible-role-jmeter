arnaudblancher.jmeter
=====================

Install a jmeter server

Copy to the server .jmx files and .properties files

Run jmeter tests and return the status

Requirements
------------

java8

Role Variables
--------------

please see [defaults/main.yml](defaults/main.yml)


Dependencies
------------

none if you have java

Example Playbook
----------------



#### Installation jmeter et execution de tous les scenarii (toutes les actions) :

```ansible-playbook -i inventory/docker/  jmeter_book.yml```

## Utilisation limitée à certaine actions

#### Installation jmeter

```ansible-playbook -i inventory/docker/ --skip-tags=jmeter_run_tests jmeter_book.yml```


#### Synchroniser les scenarii ( et uniquement cette operation)

```ansible-playbook -i inventory/docker/ --tags=jmeter_scenarii_copy jmeter_book.yml```


#### Recuperation de scenarii jmeter externes via git

```ansible-playbook -i inventory/docker --tags="jmeter-scenario-external" book_jmeter.yml```


#### Verification de la version du serveur jmeter

```ansible-playbook -i inventory/docker/ --tags=jmeter_version_check jmeter_book.yml```


#### Execution de tous les scenarii

```ansible-playbook -i inventory/docker/ --tags=jmeter_run_tests jmeter_book.yml```


#### Utilisation d'une image docker contenant jmeter2.13

cf sur dockerhub arnaudblancher/docker-ubuntu14-jmeter


### Configuration

```roles/jmeter/defaults/main.yml``` contient la configuration par defaut.

Les scenarii jmeter utilisables proviennent de deux sources :
* fichier locaux local: roles/jmeter/templates{{jmeter_scenarii_dir}}/*.jmx

* dépots git externes (voir le hash jmeter_external_scenarii_git_repositories sous roles/jmeter/defaults/main.yml)



License
-------

GPLv3

Authors Information
------------------

Arnaud Blancher

[https://github.com/arnaudblancher/ansible-role-jmeter](https://github.com/arnaudblancher/ansible-role-jmeter)

Anthony Le Mansec

