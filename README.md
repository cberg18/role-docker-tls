Role Name
=========

Creates OpenSSL certificates for Docker TLS and configures Docker to use them. Also creates client certificates for authentication.

Requirements
------------

openssl

Role Variables
--------------


dds_system_tmp
> Path to temporary file space. Defaults to '/tmp'.

dds_country
> Two character country abbreviation. Used in the server CSR. Defaults to 'US'.

dds_state
> State or provence name. Used in the server CSR. Defaults to 'Colorado'.

dds_locality
> City name. Used in the server CSR. Defaults to 'Denver'.

dds_organization
> Organization or company name. Used in the server CSR. Defaults to 'Acme Corp'.

dds_host
> The host name or IP address used to access the Docker daemon. Defaults to "{{ ansible_facts.default_ipv4.address }}".

dds_port:
> The port number used to access the Docker daemon. Defaults to '2376'.

dds_common_name:
> The common name used in the server CSR. Defaults to '{{ ansible_hostname }}'.

dds_passphrase
> A password used to secure key files. Defauts to 'Phrase123!'.

dds_server_cert_path
> Path where server certificates will be created. Defaults to '/etc/docker'.

dds_client_cert_path
> Path where client certificates will be created. Defaults to '~/.docker'.

dds_configure_docker: false
> update daemon.json to use the new TLS certificates

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role-docker-tls

License
-------

GPLv3

Author Information
------------------

Cory Berg

Inspired heavily by https://github.com/ansible/role-secure-docker-daemon
