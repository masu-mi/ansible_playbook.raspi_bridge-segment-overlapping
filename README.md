ansible_playbook.raspi_bridge-segment-overlapping
---
This playbook offers pseudo L2 bridge for a wireles Wi-Fi router that doesn't support WDS bridging with configuring a Debian family server (e.g. Raspberry Pi).

Premis: This playbook reuires following items to a target host.

* Wi-Fi access configured to existing Wi-Fi router
* ssh.service is running

Note: Because the target is a home **network** device, the playbook don't execute auto reboot, please reboot the target after run the playbook.

![target network](images/target-network.png)

## Usage

If you want to customize parameters, please read *./inventories/host.yml.example*, *.envrc.example* files.

### setup (controller)
You can setup controller node with poetry.

```sh
poetry install
poetry shell
```

### setup (target)

```sh
# in controller
ansible-playbook -i ./inventories/home.yml ./playbook.yml
ssh $remote_user@raspberrypi.local
# in target
sudo reboot now
```
