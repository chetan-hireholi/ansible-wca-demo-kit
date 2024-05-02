# README.md

## IBM watsonx Code Assistant for Red Hat Ansible Lightspeed - Simple Apache Install/Config

### Synopsis

Use this repository to do a lightweight demonstration of content generation with IBM watsonx Code Assistant for Red Hat Ansible Lightspeed. This is part of the AI-Powered IT Automation Technology Pattern.

This demo is a Simple Apache Installation and Configuration playbook that can be run on a single RHEL server.

#### Outcomes

- Know what IBM watsonx Code Assistant for Red Hat Ansible Lightspeed is, along with its capabilities and relevant use cases
- Know how to install the prerequisites to run Ansible and Ansible Lightspeed on your MacBook Pro
- Know how to install and configure the Ansible extension in VS Code
- Demonstrate how Ansible Lightspeed provides code in response to Ansible tasks in YAML-based Ansible Playbooks.

#### Summary

Contains the initial components of an Ansible playbook: a top-level play `apacheservers.yml`, and an `inventory` file. The top-level playbook uses Ansible Roles to install & configure the software and a sample `index.html` file. The directory tree and files for the roles have been pre-populated, but the tasks/main.yml files for each role need code added to each task.

### Prerequisites

- Microsoft VS Code
- homebrew
- ansible
- ansible-lint
- python3
  
### Up & Running

#### Note: This is not the demo script

> NOTE: there is an `install` script in the `demo-setup` directory but it has not been tested on a fresh macOS installation. Please follow the manual steps below.

1. Provision the servers you want to run the playbook against. These can be provisioned locally using VMware Fusion, in TechZone, or on a cloud services provider like Azure.
    1. To develop and test this demo, I reserved a TechZone instance for a single instance of RHEL 9.2 running on a POWER10 LPAR. I used [this collection][Red_Hat_or_Suse_Linux_PowerVM_POWER10_LPAR] and reserved "Red Hat or Suse Linux PowerVM POWER10 LPAR." The environment was ready within 10-20 minutes after requesting it.
        1. 1 CPU
        1. 2 GB RAM
        1. RHEL 9.2
        1. No additional disk is needed
1. Install the Command Line Tools (CLT) for Xcode with `xcode-select --install`
1. Install Microsoft VS Code on your MacBook from the Mac@IBM App Store or with `brew install --cask visual-studio-code`
1. Install Python3 with `brew install python3`
1. Install Ansible and Ansible Linting with `pip3 install ansible ansible-lint`
1. After your managed server(s) has provisioned, edit `./inventory` and update the FQDN under `[apacheservers]` with the FQDN of your provisioned server in TechZone.
1. Save the provided private SSH key to a local file, e.g., `demo.pem`.
1. Set 0400 permissions on demo.pem with `chmod 400 demo.pem`
1. Update Shortcut 2 below to reflect the FQDN of your new server.
1. Confirm that your local ansible engine can connect to the remote server using an _ad hoc_ command and the `ping` module: `ansible apacheservers -m ping -i ./inventory -b --private-key ~/.ssh/id_rsa-ansibledemo -u cecuser`.
1. Install the Ansible collections in ./roles/requirements.yml with `ansible-galaxy install -r ./roles/requirements.yml`

### Demo Script

> TIP: Watch [Pete's 24-minute Demo Video][pete_demo_video] and follow these steps as you go.

#### High-level Demo Steps

- Install/Config Ansible Extension in Microsoft VS Code
  - Search for "ansible" in Extensions and select the Red Hat-authored extension.
  - Review the Ansible Extension page briefly, then install it
    - Open VS Code Settings with Cmd-,
  - Search for "lightspeed"
  - Show the three settings, and check off the first and third ones
  - For the second setting, confirm the endpoint is `https://c.ai.ansible.redhat.com`
  - Click on the Ansible Extension in the left margin
  - Connect to the Ansible Lightspeed service using your public github.com account.
  - Confirm you see "Lightspeed" in the bottom-right portion of the VS Code window.
- Show playbook repo in VS Code
  - `inventory`
  - `apacheservers.yml` top-level play
  - contents of each role, explaining the four subfolders as you go
- Enable Ansible Lightspeed with Watson Code Assistant in VS Code
- Connect to the Lightspeed AI endpoint using your personal github.com account
- Use Lightspeed to create tasks in the following files, in order:
  - ./roles/httpd/tasks/main.yml
  - ./roles/httpd.conf/handlers/main.yml
  - ./roles/httpd.conf/tasks/main.yml
  - ./roles/index.html/tasks/main.yml
  - ./roles/openshift-binaries/tasks/main.yml
- Run the playbook from the CLI (Shortcut 1)
  - Make sure you save all of the files you modified!
  - Fix anything that needs fixing
  - Test the URL with `curl` (Shortcut 2)
  - Change `server_type` in `apacheservers.yml` from `apache` to something else, re-run the playbook, and test the endpoint with `curl` to see the change.
- Time Allowing: use Lightspeed to add a handler that tests the URL with curl, and then call the handler after `httpd` is restarted.
- Q&A

#### How to Reset the Demo

1. To reset the managed endpoint(s) to their original state, run the `reset.yml` playbook with `ansible-playbook -i ./inventory reset.yml --private-key demo.pem`.
1. To reset the local `roles` directory to its starting point, run the following two commands from the root of the playbook:
   1. `rm -rf ./roles`
   1. `tar zxvf ./demo-setup/roles.tgz`
1. To reset `apacheservers.yml` to its original state, run `cp ./demo-setup/apacheservers.yml.orig ./apacheservers.yml`

Shortcuts:

1. `ansible-playbook -i ./inventory apacheservers.yml --private-key demo.pem`
2. `curl http://FQDN.of.your.server:8080/`

### References

- [Pete's 24-minute Demo Video](https://ibm.box.com/s/a06e8ppy4wjmz8b5bmr0bd2ktgkcb4h4)
- [Ansible Lightspeed with Watson Code Assistant](https://docs.ai.ansible.redhat.com/)

### Authors

- [pete nuwayser](mailto:pnuw@ibm.com)
- [Rubayat Khan](mailto:rubayat.khan@ibm.com)

[Red_Hat_or_Suse_Linux_PowerVM_POWER10_LPAR]: https://techzone.ibm.com/collection/6261d3584670d7001e3d483a
[pete_demo_video]: https://ibm.box.com/s/a06e8ppy4wjmz8b5bmr0bd2ktgkcb4h
