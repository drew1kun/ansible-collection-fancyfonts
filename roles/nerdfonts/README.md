# Ansible role: nerdfonts

[![MIT licensed][mit-badge]][mit-link]
[![Galaxy Role][role-badge]][galaxy-link]

Description
----

Cross-platform ansible role for [NerdFonts][nerdfonts] ([on GitHub][nf-git]) installation.

Requirements
----

One of the following OS (or deriviatives):

 - Debian | Ubuntu
 - MacOS (with [Homebrew][homebrew])

**NOTE:**

 - Role requires Fact Gathering by ansible!
 - On MacOS only user-specific installation from Homebrew is available

**MacOS:**
if Homebrew is not installed on the managed host, install the following role via galaxy:

```
ansible-galaxy install geerlingguy.homebrew
```

 And include it in the playbook:
 
```yaml
roles:
  - geerlingguy.homebrew
```

Role Variables
----

OS-Agnostic ([`defaults/main.yml`](defaults/main.yml)):

| Variable | Description | Default |
|----------|-------------|---------|
| `nerdfonts_fonts[]` | List of nerdfonts to be installed | see [`defaults/main.yml`](defaults/main.yml) |
| `nerdfonts_users[]` | List of users nerdfonts to be installed | see [`defaults/main.yml`](defaults/main.yml) |

Debian-Specific ([`defaults/debian.yml`](defaults/debian.yml)):

| Variable | Description | Default |
|----------|-------------|---------|
| `nerdfonts_release` | Release version (see [here](https://github.com/ryanoasis/nerd-fonts/releases)) | `v2.3.1` | 
| `nerdfonts_env` | Install fonts `system`-wide or `user`-wide | `system` |
| `nerdfonts_sys_dir` | System-wide fonts directory | `/usr/local/share/fonts` |
| `nerdfonts_usr_dir` | User-specific fonts directory | `~/.local/share/fonts` |
| `nerdfonts_install_dir` | User-specific fonts directory | see [`defaults/debian.yml`](defaults/debian.yml) |


Dependencies
----

None

Example Playbook
----

```yaml
- hosts: dev_clients_macos
  gather_facts: yes
  roles:
  	- geerlingguy.homebrew
  	- drew1kun.nerdfonts
```

License
----

[MIT][mit-link]

Author Information
----

Andrew Shagayev | [e-mail](mailto:drewshg@gmail.com)

[role-badge]: https://img.shields.io/badge/role-drew1kun.nerdfonts-green.svg
[galaxy-link]: https://galaxy.ansible.com/drew1kun/nerdfonts/
[mit-badge]: https://img.shields.io/badge/license-MIT-blue.svg
[mit-link]: https://raw.githubusercontent.com/drew1kun/ansible-nerdfonts/master/LICENSE
[homebrew]: http://brew.sh/
[nerdfonts]: https://nerdfonts.com/
[nf-git]: https://github.com/ryanoasis/nerd-fonts
