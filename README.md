devstack
========

[![Build Status](https://travis-ci.org/dstanek/ansible-role-keystone-sp.svg?branch=master)](https://travis-ci.org/dstanek/ansible-role-keystone-sp)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-dstanek.keystone-sp-blue.svg)](https://galaxy.ansible.com/dstanek/keystone-sp/)

A role to install and run keystone as a SAML2 service provider.

Requirements
------------

None

Role Variables
--------------

TODO(dstanek): fill this out.

Dependencies
------------

None

Example Playbook
----------------

Install and run keystone as a service provider for the testshib IdP:

    - name: Setup a keystone service provider using testshib
      hosts: all
      gather_facts: true
      remote_user: root
      vars:
        admin_os_cloud: devstack-admin
        keystone_sp_idps:
          - name: testshib
            remote_id: https://idp.testshib.org/idp/shibboleth
            metadata_uri: http://www.testshib.org/metadata/testshib-providers.xml
        keystone_sp_hostname: "{{ inventory_hostname }}"
        keystone_sp_dashboard_hostname: "{{ inventory_hostname }}"
      roles:
        - dstanek.keystone-sp

License
-------

Apache 2.0

Author Information
------------------

David Stanek <dstanek@dstanek.com>

http://traceback.org
