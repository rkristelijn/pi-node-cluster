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
perl: warning: Setting locale failed.
perl: warning: Please check that your locale settings:
	LANGUAGE = (unset),
	LC_ALL = (unset),
	LC_MONETARY = "nl_NL.UTF-8",
	LC_ADDRESS = "nl_NL.UTF-8",
	LC_TELEPHONE = "nl_NL.UTF-8",
	LC_NAME = "nl_NL.UTF-8",
	LC_MEASUREMENT = "nl_NL.UTF-8",
	LC_IDENTIFICATION = "nl_NL.UTF-8",
	LC_NUMERIC = "nl_NL.UTF-8",
	LC_PAPER = "nl_NL.UTF-8",
	LANG = "en_GB.UTF-8"
    are supported and installed on your system.
perl: warning: Falling back to a fallback locale ("en_GB.UTF-8").
```

[reference](https://www.thomas-krenn.com/en/wiki/Perl_warning_Setting_locale_failed_in_Debian)

**Generating locales**

Missing locales are generated with locale-gen:

`sudo locale-gen en_US.UTF-8`

Alternatively a locale file can be created manually with localedef:

`sudo localedef -i en_US -f UTF-8 en_US.UTF-8`

**Setting Locale Settings**

The locale settings can be set (to en_US.UTF-8 in the example) as follows:

```
export LANGUAGE=en_US.UTF-8
export LANG=en_US.UTF-8
sudo dpkg-reconfigure locales
```
---

Doesn't work...

**New try**

[reference](https://www.raspberrypi.org/blog/another-update-raspbian/)

```
sudo apt-get update
sudo apt-get dist-upgrade
sudo apt-get install piclone geany usb-modeswitch pi-bluetooth
sudo apt-get install python-pigpio python3-pigpio
```

---
or just download the network version of the latest NOOBS

- format sd card as FAT,
- upzip the files

[reference](https://www.raspberrypi.org/documentation/installation/noobs.md)

---

`sudo raspi-config`

Enable locale `nl_NL.UTF-8 UTF-8`
Default:`en_US`

```
git clone https://github.com/raspberrypi-ui/piclone
cd piclone
./autogen.sh
```
autoreconf: not found

`sudo apt-get install autoconf`
