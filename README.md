# ansible-pihole
Ansible playbook for deploying pihole in docker, along with helpers/metrics

This is work in progress.

To install dependencies, run:
`ansible-galaxy install -r requirements.yml && ansible-galaxy collection install -r requirements.yml`

To run the playbook, copy the `inventory.example` file to `inventory`, modify it to reflect the hosts you want this to run on ([How to build your inventory - Asible Docs](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html)), and then:
`ansible-playbook main.yml -i inventory`