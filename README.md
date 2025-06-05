# Shadowsocks to Tor Setup

This project provides Ansible playbooks to set up a Shadowsocks server on your VPS and route all its traffic through Tor. For more details and explanations, see the [blog post](https://bogomolov.work/blog/posts/shadowsocks-to-tor/). Note that not all features may work as expected.

## Prerequisites

- A VPS with SSH access.
- Python 3 and `pip` installed on your local machine.
- Ansible installed (see installation steps below).
- Basic knowledge of Ansible and inventory configuration.

## Installation and Usage

To run the playbooks locally, follow these steps:

1. Set up a virtual environment:
   ```bash
   python3 -m venv ./venv
   ```
1. Activate the virtual environment:
   ```bash
   source ./venv/bin/activate
   ```
1. Install Ansible:
   ```bash
   pip install ansible
   ```
1. Configure your inventory file based on the example inventory file:
   ```bash
   cp inventory.example.yaml inventory.yaml
   ```
   Edit _inventory.yaml_ with your VPS details (e.g., host, user, and SSH key).
1. Run the server playbook:
   ```bash
   ansible-playbook -i inventory.yaml server.yaml
   ```
1. (Optional) Run the client playbook, replacing `YOUR_ACTUAL_SS_PASSWORD` with your Shadowsocks password:
   ```bash
   ansible-playbook -i inventory.yaml client.yaml --extra-vars "ss_password=YOUR_ACTUAL_SS_PASSWORD"
   ```

## Notes

- Ensure your VPS has the necessary dependencies installed by the playbook.
- The client playbook requires a valid Shadowsocks password for configuration.
- Refer to the [blog post](https://bogomolov.work/blog/posts/shadowsocks-to-tor/) for troubleshooting and additional context.
