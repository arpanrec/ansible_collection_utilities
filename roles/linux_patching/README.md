# Ansible Role Linux Patching (arpanrec.utilities.linux_patching)

Install all latest packages in Debian based systems. also Install basic utility tools for server.
Set timezone, locale, and loopback ip in server

## Role Variables

- `rv_linux_patching_upgrade_existing_packages`

  - Description: If set to `true` Upgrade the existing packages in OS.
  - Required: `false`
  - Default: `true`
  - Type: `bool`

- `rv_linux_patching_packages`

  - Description: Install the packages in all the distributions.
  - Required: `false`
  - Default: [ `zip`, `unzip`, `net-tools`, `build-essential`, `tar`, `wget`, `curl`, `ca-certificates`, `sudo`, `systemd`, `telnet`, `gnupg2`, `apt-transport-https`, `lsb-release`, `software-properties-common`, `locales`, `"linux-headers-{{ansible_kernel}}"`, `network-manager`, `gnupg2`, `gnupg`, `pigz`, `cron`, `acl` , `fontconfig`, `gtk-update-icon-cache`, `libnss3`, `libatk1.0-0`, `libatk-bridge2.0-0`, `libgtk-3-0`, `bzip2`, `libgbm-dev`, `libglib2.0-dev`, `libdrm-dev`, `libasound2`, `jq`, `zsh`, `ntfs-3g`, `exfat-fuse`, `exfat-utils`]
  - Type: `list[str]`

- `rv_linux_patching_timezone`

  - Description: Set the ZoneTime info in server.
  - Required: `false`
  - Default: `Asia/Kolkata`
  - Type: `str`

- `rv_linux_patching_hostname`

  - Description: Cluster / Public Host name. (Doesn't work with docker)
  - Required: `false`
  - Type: `str`

- `rv_linux_patching_root_ca_pem_content`
  - Description: Organization Root CA certificate.
  - Required: `false`
  - Type: `str`

## Example Playbook

```yaml
---
- name: Patch Debian System
  become: true
  become_method: su
  any_errors_fatal: true
  ansible.builtin.import_role:
    name: arpanrec.utilities.linux_patching
```
