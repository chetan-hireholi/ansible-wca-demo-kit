# Install and configure PostgreSQL and PGAdmin container using Ansible Lightspeed

## Overview

The demo consists for two Ansible Playbooks that performs the following tasks respectively:

- Installs `postgresql-server`, initializes the database, and starts and enables the `postgresql` service.
- Uses `podman` to configure and run the **dpage/pgadmin4** as a service.

This demo illustrates the following Ansible Lightspeed features:

- Translating easy-to-understand prompts into syntactically correct Ansible content without needing in depth knowledge of the automated technology.
- Using keywords, such us `....using X var`, in prompts to obtain desired suggestions.
- Using the full YAML file context to generate Ansible content with best practices.

_Thanks to Craig Brandt for the example._
_Link to main github repo:_ https://github.com/craig-br/lightspeed-demos/blob/main/playbooks/infra/install_pgsql_and_pgadmin/README.md