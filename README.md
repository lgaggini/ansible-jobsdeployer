# ansible-jobsdeployer

ansible-jobsdeployer is an Ansible role to install and configure jobs on a debian based OS.

It performs: 

* creation of dedicated user and group for jobs execution
* creation of dedicated folder for jobs home
* deploy of source code from git
* installation of project dependencies by virtualenv, pip and os packages
* scheduling of jobs by user cron

## Install
### Clone
```bash
git clone https://github.com/lgaggini/ansible-jobsdeployer.git
```
## Configuration

The configuration is done by vars listed and explained in [defaults/main.yml](https://github.com/lgaggini/ansible-jobsdeployer/blob/master/defaults/main.yml) file.

## Usage

```
- name: bootstrap an ubuntu cloud image for jobs
  hosts: jobserver
  vars_files:
    - group_vars/jobsdeployer.yml

  roles:
    - { role: jobsdeployer, tags: ['jobsdeployer'] }
```
