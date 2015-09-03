# ModXpedite

Start new Modx projects quickly.

## Installation

1. Install Vagrant, Virtualbox and Ansible
2. Clone this repository
3. Change into the cloned directory
4. Run `vagrant up`

A virtual machine will be created, based on Ubuntu 14.04, with the latest available versions of the following software installed:

- Apache2
- PHP
- MySQL
- Modx
- Gitify

## Usage

Visit [http://localhost:8080/manager/](http://localhost:8080/manager/) in your browser to log into the Modx dashboard.

The default Modx admin account is `admin` and the password is `password`.

You can develop your site in Modx as usual.

### Accessing and navigating around the virtual machine

- Type `vagrant ssh` from within the ModXpedite directory (cloned from github) to log into the virtual machine.
- The default MySQL account is `root`. There is no password.
- The Modx web root is `/var/vhost/modx`.
- The ModXpedite directory (cloned from Github) is mounted at `/vagrant` inside the virtual machine

### Gitify

[Gitify](https://github.com/modmore/Gitify/) is a tool that can extract Modx data to a file structure so that it can be committed to git. Such a workflow might look like this:

1. Do some work in Modx.
2. From the web root of the virtual machine, run `gitify extract`. The contents of the Modx database are exported. They are stored in the `modx` subdirectory of the ModXpedite directory - outside the VM.
3. Commit the contents of the `modx` directory to git.

The process can be reversed if you want to work in an external editor and then import your changes into Modx: use the `gitify build` command. This can also be used to move a site between Modx instances, for example, from development to staging or production.

Detailed instructions for using Gitify are on the [Gitify wiki](https://github.com/modmore/Gitify/wiki/2.-Available-Commands).
