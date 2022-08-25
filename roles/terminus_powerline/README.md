Ansible role: terminus_powerline
=========

[![MIT licensed][mit-badge]][mit-link]
[![Galaxy Role][role-badge]][galaxy-link]

Cross-platform ansible role for installation of [Terminus font][terminus-git] (patched with [Powerline][powerline-git] symbols)

Requirements
------------

NOTE: Role requires Fact Gathering by ansible!

One of the following OS (or deriviatives):
 - Debian
 - MacOS (with [Homebrew][homebrew])

For MacOS:
if Homebrew is not installed on the managed host, install the following role via galaxy:

    ansible-galaxy install drew1kun.homebrew

 And include it in the playbook:

```yaml
roles:
- geerlingguy.homebrew
```

Role Variables
--------------

OS-Agnostic:


    terminus_powerline_users:                       # list of users if running user-specific installation

| Variable | Description | Default |
|----------|-------------|---------|
| **terminus_powerline_env** | system | user/users -- install font system-wide or user-wide (On MacOS font always will be installed system-wide) | <ul><li>Darwin: `/Library/Fonts/`</li><li>Debian: `/usr/local/share/fonts`</li></ul> |
| **terminus_powerline_users** | list of users if running user-specific installation | <ul><li>Darwin: `/Library/Fonts/`</li><li>Debian: `/usr/local/share/fonts`</li></ul> |

OS-Specific:

| Variable | Description | Default |
|----------|-------------|---------|
| **terminus_powerline_fonts_dir** | Directory the fonts installed to | <ul><li>Darwin: `/Library/Fonts/`</li><li>Debian: `/usr/local/share/fonts`</li></ul> |

Dependencies
------------

None

Example Playbook
----------------

For MacOS:

```yaml
- hosts: dev_clients_macos
  gather_facts: yes
  roles:
  - drew1kun.homebrew
  - drew1kun.terminus_powerline
```

For Linux:

```yaml
- hosts: dev_clients_linux
  gather_facts: yes
  roles:
  - drew1kun.terminus_powerline
```

License
-------

[MIT][mit-link]

Author Information
------------------

Andrew Shagayev | [e-mail](mailto:drewshg@gmail.com)

[role-badge]:https://img.shields.io/badge/role-drew--kun.terminus__powerline-green.svg
[galaxy-link]: https://galaxy.ansible.com/drew1kun/terminus_powerline/
[mit-badge]: https://img.shields.io/badge/license-MIT-blue.svg
[mit-link]: https://raw.githubusercontent.com/drew1kun/ansible-terminus_powerline/master/LICENSE
[homebrew]: http://brew.sh/
[terminus-git]: https://github.com/drew1kun/terminus_powerline_font_osx
[powerline-git]: https://github.com/powerline/fonts
