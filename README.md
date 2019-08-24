acs
=========

[![Build Status](https://travis-ci.org/sirReeall/acs.svg?branch=master)](https://travis-ci.org/sirReeall/acs)

Performs the following actions:
1. Downloads Alfresco Content Services 6.1 from Nexus (this requires Nexus credentials which must be obtained from Alfresco Customer Support)
2. Extracts the downloaded zip to the specified acs_install_folder directory

Requirements
------------

This uses [Ansilble Unarchive](https://docs.ansible.com/ansible/latest/modules/unarchive_module.html) module which requires gtar or unzip to be installed on the target host.

The acs_install_folder can be created before hand, however it must be empty. **If the directory is not empty, all other tasks will be skipped for safty.**

Role Variables
--------------

**Manditory Variables**

Both **nexus_user** and **nexus_password** must be specified when using this role. 
There are a number of ways to do this, for example:
1. Passing at the command line using --extra_vars **(not recommended)**
2. Using var_prompt
3. Using ansible-vault

| Name | Default | Remarks |
| --- | --- | --- |
| acs_install_folder | /opt/alfresco | The location where the zip file is download and extracted |
| acs_user | alfresco | The user account that will own the extracted files and acs_install_folder |
| nexus_user |  | **Manditory** |
| nexus_password |  | **Manditory** |
| nexus_url | https://artifacts.alfresco.com/nexus/content/groups/internal/org/alfresco/alfresco-content-services-distribution/6.1.0/alfresco-content-services-distribution-6.1.0.zip | URL to zip file |

Example Playbook
----------------

Here is how to user var_prompts to run this role

```yaml
- hosts: all
  vars_prompt:
    - name: nexus_user
      prompt: "Please specify your Maven username: "
      private: no

    - name: nexus_password
      prompt: "Please specify your Maven password: "
      private: yes
      encrypt: "sha512_crypt"
  
  include_role: 
    name: acs
```

License
-------

Free
