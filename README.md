ufw
=========

_Installs ufw, maintain application profiles and rules._

Requirements
------------

Ansible 2.5 or above is highly recommended.

Role Variables
--------------

    ufw_package_state: present
    ufw_firewall_state: enabled
    ufw_rules:
      - rule: allow
        port: 8080
        src: example.com
    ufw_applications:
      - name: Grafana
        title: Grafana
        description: Dashboard and graph generator
        ports:
          - 3000/tcp
        sources:
          - 127.0.0.1
          - "{{ lookup('dig', 'example.com') }}"
          
Dependencies
------------

    hyperized.package

Example Playbook
----------------

    - hosts: all
      become: yes
      roles:
        - role: hyperized.ufw

License
-------

MIT

Author Information
------------------

Gerben Geijteman <gerben@hyperized.net>
