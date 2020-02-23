# Ansible Rails

Ansible playbook to setup a web server for a Rails application. 

Components: Nginx, PostgreSQL, Redis, Ruby, Nodejs, Monit, Let's Encrypt,
Utilities (acmetool, git, htop, tmux, tree, wget, rclone, etc.). Rails
application is served via Puma application server.

_Note: unpolished since 2019._

# Requirements

+ Server: CentOS 7 and upper (with SElinux disabled)
+ Client: Ansible 2.7 and upper

# Configuration

Copy `group_vars/all.yml.example` to `group_vars/all.yml` and set values.

Set server IP address and port in `production` file.

Modify other values based on your needs.

# Usage

Initial run:

1. Run `ssh-keyscan -t rsa SERVER_IP >> ~/.ssh/known_hosts`

2. Run `ansible-playbook site.yml -i production -e ansible_port=22 -k -f 10`

After initial:

Just run `ansible-playbook site.yml -i production -f 10`

## License

Released under the BSD 2-clause license. See LICENSE.txt for details.
