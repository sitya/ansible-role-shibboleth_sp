# Shibboleth SP - Ansible role

This role installs and configures a Shibboleth2 SP on Debian based systems.

## Role Variables
    shibboleth_sp:
      host: sp.example.org
      federation_signer_certificate_url: https://your-federation.com/federation_signer_certificate.crt
      federation_metadata_url: http://your-federation.com/federation.xml
      certificate_subject: "C=HU/ST=Your state/L=Your city/O=Your Company"
      certificate_mail: info@example.org

Don't forget to override these default values.

## Dependencies

None

## Author Information

Tamas Frank <sitya@niif.hu>