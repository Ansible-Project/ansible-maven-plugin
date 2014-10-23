# Ansible Maven Plugin 

A [maven plugin](http://maven.apache.org/plugins/index.html) to simplify the running 
of [Ansible](http://docs.ansible.com/) [playbooks](http://docs.ansible.com/playbooks.html) from within Maven

## Goals Overview

* [ansible:ansible](#ansible) executes an ansible module, using the ansible executable
* [ansible:playbook](#playbook) runs an ansible playbook, using the ansible-playbook executable

## Usage

See the [integration tests](src/it) for examples of using the plugin within a project

### ansible
```
  mvn co.escapeideas.maven:ansible-maven-plugin:ansible -DmoduleName=ping -Dhosts=localhost
```  

Executes the ansible __ping__ module with the host as __localhost__

### playbook
```
  mvn co.escapeideas.maven:ansible-maven-plugin:playbook -Dplaybook=playbook.yml 
```  

Runs the playbook __playbook.yml__

## Goals
<a id="ansible"></a>
### ansible

Binds by default to the [lifecycle phase](http://maven.apache.org/ref/current/maven-core/lifecycles.html): _pre-integration-test_

####Parameters
  Name | Type | Description | Required
  :----|:----:|:------------|:-------:
  background|Integer|Run asynchronously, failing after this number of seconds|No
  connection|String|Connection type to use|No
  executable|String|The executable to use for this execution, defaults to ansible|Yes
  forks|Integer|The number of parallel processes to use|No
  hosts|String|Pattern for matching hosts to run the module against, defaults to localhost|Yes
  inventory|File|The inventory host file|No
  limit|String|Limit selected hosts to an additional pattern|No
  moduleArgs|String|Module arguments|No
  moduleName|String|Module name to execute, defaults to ping|Yes
  modulePath|File|The path to the ansible module library|No
  pollInterval|Integer|The poll interval if using background|No
  privateKey|File|Use this file to authenticate the connection|No
  remoteUser|String|Connect as this user|No
  timeout|Integer|Override the SSH timeout in seconds|No
  vaultPasswordFile|File|Vault password file|No
  workingDirectory|File|The directory in which to run, defaults to the projects basedir|Yes
  
<a id="playbook"></a>
### playbook
Binds by default to the [lifecycle phase](http://maven.apache.org/ref/current/maven-core/lifecycles.html): _pre-integration-test_

####Parameters
  Name | Type | Description | Required
  :----|:----:|:------------|:-------:
  background|Integer|Run asynchronously, failing after this number of seconds|No
  connection|String|Connection type to use|No
  executable|String|The executable to use for this execution, defaults to ansible|Yes
  forks|Integer|The number of parallel processes to use|No
  hosts|String|Pattern for matching hosts to run the module against, defaults to localhost|Yes
  inventory|File|The inventory host file|No
  limit|String|Limit selected hosts to an additional pattern|No
  moduleArgs|String|Module arguments|No
  moduleName|String|Module name to execute, defaults to ping|Yes
  modulePath|File|The path to the ansible module library|No
  pollInterval|Integer|The poll interval if using background|No
  privateKey|File|Use this file to authenticate the connection|No
  remoteUser|String|Connect as this user|No
  timeout|Integer|Override the SSH timeout in seconds|No
  vaultPasswordFile|File|Vault password file|No
  workingDirectory|File|The directory in which to run, defaults to the projects basedir|Yes
