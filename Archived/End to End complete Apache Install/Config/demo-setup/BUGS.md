# Lightspeed Bugs We Found

## Installing Homebrew requires Homebrew to already be installed

```Ansible
- name: Installing Homebrew
  community.general.homebrew:
    name: "{{ Brew_packages }}"
    state: present
    install_options: "{{ Brew_packages }}"
    upgrade_all: true
  when:
    - homebrew_check.rc != 0
```

Pete:
> I would have expected this to install homebrew from [http://brew.sh](http://brew.sh) or with `xcode-select --install`

Raimond:
> `xcode-select --install` does not install `brew`. The Command Line Tools (CLT) for Xcode used to be a prerequisite for `brew`, used to be because I have seen recent posts from people who install `brew` w/o the CLT.

## Instructing Lightspeed to unarchive two local files to a remote directory

```Ansible
---
# install openshift-client & openshift-install 4.8.52

- name: unarchive local tarballs fake-openshift-client-linux.tar.gz and fake-openshift-install-linux.tar.gz to /usr/local/bin on remote with mode 0755
  ansible.builtin.unarchive:
    src: "{{ item }}"
    dest: /usr/local/bin
    mode: '755'
    remote_src: true
  loop:
    - /tmp/openshift-client-linux.tar.gz
    - /tmp/openshift-install-linux.tar.gz
```

Pete:
> need to change 755 to 0755; need to delete the remote_src line; need to remove the /tmp/ prefix from the two file names, and need to prepend "fake-" to each filename. What's interesting is that, if you fix it and then repeat the same `-name:` line later in the file, it gets the file names right.
