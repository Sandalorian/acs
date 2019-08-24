#Work in progress and no where near ready :)


acs
=========

Performs the following actions by default:
1. Downloads Alfresco Content Services 6.1 from Nexus (this requires Nexus credentials which must be obtained from Alfresco Customer Support)
2. Installs and configures the ACS 6.1 war files into Tomcat.
3. Configures Tomcat so the war files can be deployed.
4. TBC


Requirements
------------

Quite a few. This is work in progress.

This use Ansilble Unarchive module which requires gtar or unzip to be installed on the target host.

The acs_install_folder can be created before hand, however it must be empty. If the directory is not empty, all other tasks will be skipped for safty.

Role Variables
--------------

Quite a few. This is work in progress.

Dependencies
------------

Quite a few. This is work in progress.

Example Playbook
----------------

License
-------

Free
