Shibboleth SP - Ansible role
========

This role installs and configures a Shibboleth2 SP against Azure AD, supports CentOS/Debian/Fedora based systems.

[![Build Status](https://travis-ci.org/jpgimenez/ansible-shibboleth_sp-azure_ad.svg?branch=master)](https://travis-ci.org/jpgimenez/ansible-shibboleth_sp-azure_ad)

Requirements
------------

This role requires Ansible 1.4 or higher and platform requirements are listed in the metadata file.

Role Variables
--------------

    # sample configuration
    # replace "contoso.com" with your "tenant id"
    #
    shibboleth_sp:
          host: localhost
          webserver: apache
          federation_metadata_url: https://login.microsoftonline.com/contoso.com/federationmetadata/2007-06/federationmetadata.xml
          federation_signer_certificate_url: False
          default_idp: https://sts.windows.net/contoso.com/
          certificate_subject: "C=HU/ST=Your state/L=Your city/O=Your Company"
          certificate_mail: info@example.org

#### host:
Your AD domain name

#### federation_metadata_url:
URL of AD FederationMetadata.xml

#### default_idp:
You can found this value inside federation metadata xml, under entityID attribute.

#### certificate_*:
shibboleth uses a self signed certificate, this values are used on the generation of that certificate.

Don't forget to override these default values.

Testing
-------

Create a test_vars.yml file and define role variables.

To test with default vagrant vm:

	$ vagrant up test

You can test against other distros too, ej. f23:

	$ vagrant up f23

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
