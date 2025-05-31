# Shadowsocks-Tor

Bootstrap your VPS by setupping shadowsocks server and passing all it traffic thru Tor.

## Details

To execute it locally:
1. setup [virtualenv](https://virtualenv.pypa.io/en/latest/) by `python3 -m venv ./venv`;
1. activate env by `source ./venv/bin/activate`;
1. add dependencies `pip install ansible`.
1. setup `inventory.yaml`, [like](https://docs.ansible.com/ansible/latest/getting_started/get_started_inventory.html#inventories-in-ini-or-yaml-format):
   ```
server:
  srv:
    hostname:
      ansible_host: <address of host>
   ```
1. execute `ansible-playbook -i inventory.yaml server.yaml`
1. execute `ansible-playbook -i inventory.yaml client.yaml`
