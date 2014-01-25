Shibboleth SP - Ansible role
========

This role installs and configures a Shibboleth2 SP on Debian based systems.

Requirements
------------

This role requires Ansible 1.4 or higher and platform requirements are listed in the metadata file.

Role Variables
--------------

    shibboleth_sp:
      host: sp.example.org
      federation_signer_certificate_url: https://your-federation.com/federation_signer_certificate.crt
      federation_metadata_url: http://your-federation.com/federation.xml
      certificate_subject: "C=HU/ST=Your state/L=Your city/O=Your Company"
      certificate_mail: info@example.org


Dependencies
------------

None

License
-------

BSD

Author Information
------------------

Tamas Frank <sitya@niif.hu>
