# Ansible Role: SSHD Hardening (arpanrec.utilities.ssh_hardening)

This role applies basic security settings for personal VPS

## Variables

`rv_sshd_hardening_ssh_port`

- Type: `int`
- Default: `22`
- Required: `false`
- Description: SSHD Server port.

`rv_sshd_hardening_ssh_security_password_authentication`

- Type: `boolean`
- Default: `true`
- Required: `false`
- Description: To disable tunneled clear text passwords.

`rv_sshd_hardening_ssh_security_permit_root_login`

- Type: `boolean`
- Default: `true`
- Required: `false`
- Description: Specifies whether root can log in using ssh.

`rv_sshd_hardening_ssh_security_permit_empty_passwords`

- Type: `boolean`
- Default: `false`
- Required: `false`
- Description: When password authentication is allowed, it specifies whether the server allows login to accounts with empty password strings.

`rv_sshd_hardening_ssh_security_max_auth_tries`

- Type: `int`
- Default: `3`
- Required: `false`
- Description: Specifies the maximum number of authentication attempts permitted per connection. Once the number of failures reaches half this value, additional failures are logged.

`rv_sshd_hardening_ssh_security_x11_forwarding`

- Type: `boolean`
- Default: `false`
- Required: `false`
- Description: Specifies whether X11 forwarding is permitted.

`rv_sshd_hardening_ssh_security_client_alive_interval`

- Type: `int`
- Default: `60`
- Required: `false`
- Description: Sets a timeout interval in seconds after which if no data has been received from the client.

`rv_sshd_hardening_ssh_security_client_alive_count_max`

- Type: `int`
- Default: `3`
- Required: `false`
- Description: Sets the number of client alive messages which may be sent without sshd(8) receiving any messages back from the client. If this threshold is reached while client alive messages are being sent, sshd will disconnect the client, terminating the session.

`rv_sshd_hardening_ssh_security_restart_service`

- Type: `bool`
- Default: `true`
- Required: `false`
- Description: Restart sshd handlers

`rv_sshd_hardening_ssh_security_challenge_response_authentication`

- Type: `bool`
- Default: `false`
- Required: `false`
- Description: Challenge-response passwords (beware issues with some PAM modules and threads)

## Example Playbook

```yaml
- name: SSHD Hardening
  ansible.builtin.include_role:
    name: arpanrec.utilities.ssh_hardening
  vars:
    rv_sshd_hardening_ssh_security_password_authentication: true
```
