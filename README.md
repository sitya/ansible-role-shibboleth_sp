Shibboleth SP - Ansible role
========

This role installs and configures a Shibboleth2 SP against Azure AD, supports CentOS/Debian/Fedora based systems.

Requirements
------------

This role requires Ansible 1.4 or higher and platform requirements are listed in the metadata file.

Role Variables
--------------

    shibboleth_sp:
      host: sp.example.org
      default_idp: https://sts.windows.net/your-azure_ad_idp/
      federation_metadata_url: http://your-federation.com/federation.xml
      certificate_subject: "C=HU/ST=Your state/L=Your city/O=Your Company"
      certificate_mail: info@example.org

Don't forget to override these default values.

Dependencies
------------

None

License
-------

BSD

Author Information
------------------

* Juan Pablo Giménez <jpg@rosario.com>
* base on https://github.com/sitya/ansible-role-shibboleth_sp/ - Tamas Frank <sitya@niif.hu>
