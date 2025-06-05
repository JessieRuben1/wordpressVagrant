# WordPress IAC Vagrant Environment

This project provisions a local Ubuntu 20.04 (focal64) virtual machine with Apache, PHP, MySQL, and WordPress using [Vagrant](https://www.vagrantup.com/).

## Features

- Ubuntu 20.04 LTS (focal64) base box
- Apache2 web server with PHP and required extensions
- MySQL server with a pre-created `wordpress` database and user
- Automated WordPress download and configuration
- Apache virtual host for WordPress
- Private and public network interfaces

## Requirements

- [Vagrant](https://www.vagrantup.com/downloads)
- [VirtualBox](https://www.virtualbox.org/) (or another supported provider)

## Usage

1. **Clone or copy this repository.**
2. **Start the VM:**
   ```sh
   vagrant up
   ```
3. **Access WordPress:**
   - Open your browser and go to [http://192.168.33.10](http://192.168.33.10) (default private network IP).
   - Complete the WordPress installation steps in your browser.

## Default Credentials

- **MySQL Database:** `wordpress`
- **MySQL User:** `wordpress`
- **MySQL Password:** `root123`

## Customization

- To change the VM resources, edit the `vb.memory` value in the [Vagrantfile](wordpress_IAC/Vagrantfile).
- To change the private IP, modify the `config.vm.network "private_network"` line.

## Cleanup

To stop and remove the VM:

```sh
vagrant halt
vagrant destroy
```

## Notes

- The VM is provisioned using an inline shell script.
- WordPress files are located in `/srv/www/wordpress` inside the VM.
- The Apache virtual host is configured for WordPress and enabled by default.

---
