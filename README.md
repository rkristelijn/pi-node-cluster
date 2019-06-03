# pi-node-cluster

These are my notes to build a JavaScript tech cluster using 3 raspberry pis.

The goals is to learn about multi server, different tech used such as Ansible, Docker, nginx, mongodb, node, networking, security, performance, monitoring... 

Questions I have:
1. how to organize user management?
2. could I pull this off using only vim?
3. How to work with docker?
4. How to monitor these systems?
5. How to benchmark, and against what?
6. How can I do this as secure as possible?

# OS install
Hold SHIFT while booting, flagging only Raspbian Lite.

Login using user:pi, password:raspberry

After login: 

- Enable ssh: `sudo raspi-config`, `5 Interface Options`, `P2 SSH`, Would you like the SSH server to be enabled? `<Yes>`
- Change hostname in network options

# Cloning SD cards for other pi-s

`sudo apt-get install git`

Some warnings for perl... idk

```
git clone https://github.com/raspberrypi-ui/piclone
cd piclone
./autogen.sh
```
autoreconf: not found


