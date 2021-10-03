# ansible-pihole
Ansible playbook for deploying pihole in docker, along with helpers/metrics

This is work in progress.

To install dependencies, run:
`ansible-galaxy install -r requirements.yml && ansible-galaxy collection install -r requirements.yml`

To run the playbook:
    1. Copy the `inventory.example` file to `invetory`, and modify it to reflect the hosts you want to install on. ([How to build your inventory - Asible Docs](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html))
    2. Copy the `vars.default.yml` file to `vars.yml`, and change the variables to reflect your own setup preferences.
    3. Run `ansible-playbook main.yml -i inventory -K` to run the playbook.

What the playbook will do:
    1. Install docker and docker-compose (also ensure the user is added to the docker group)
    2. Updates the host to disable the DNSStubResolver of systemd-resolved
    3. Installs pihole using a compose file
    4. [Optional] Installs pihole-node-exporter using a compose file, and sets it up to gather info from the pihole instance
    5. [Optional] Installs portainer-agent
    6. [Optional] Registers the portainer agent to a portainer instance
    7. [Optional] Install prometheus-node-exporter