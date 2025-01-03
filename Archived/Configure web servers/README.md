## Install and configure webserver

This playbook does the following:
1. Installs `httpd`
2. Copy the `httpd.conf.j2` file which is a template for a basic Apache config file, using Ansible best practices
3. Start and enable `httpd` services