# Ansible Collection - drew1kun.fancyfonts

[![MIT licensed][mit-badge]][mit-link]
[![Galaxy Role][collection-badge]][galaxy-link]

This collection contains Ansible roles to install [Nerdfonts][nerdfonts] and [Terminus Powerline][terminus-git] on Mac and Linux hosts.
It is also a dependency for my workstation setup Ansible playbook.

The roles included:

  - `drew1kun.nerdfonts` ([doc](https://github.com/drew1kun/ansible-collection-fancyfonts/blob/main/roles/nerdfonts/README.md))
  - `drew1kun.terminus_powerline` ([doc](https://github.com/drew1kun/ansible-collection-fancyfonts/blob/main/roles/terminus_powerline/README.md))

## Installation

Install via Ansible Galaxy:

```
ansible-galaxy collection install drew1kun.fancyfonts
```

Or include this collection in your playbook's `requirements.yml` file:

```yaml
---
collections:
- name: drew1kun.fancyfonts
```
And run:
```
ansible-galaxy install -r requirements.yml
```

## Usage

Example of the play:

```yaml
- hosts: localhost
  connection: local
  roles:
    - drew1kun.fancyfonts.nerdfonts
    - drew1kun.fancyfonts.terminus_powerline
```

## License

[MIT][mit-link]

## Author Information

Andrew Shagayev | [e-mail](mailto:drew-kun@protonmail.com)

[collection-badge]: https://img.shields.io/badge/collection-drew1kun.fancyfonts-green.svg
[galaxy-link]: https://galaxy.ansible.com/drew1kun/fancyfonts

[mit-badge]: https://img.shields.io/badge/license-MIT-blue.svg
[mit-link]: https://raw.githubusercontent.com/drew1kun/ansible-collection-fancyfonts/main/LICENSE

[nerdfonts]: https://nerdfonts.com/

[terminus-git]: https://github.com/drew1kun/terminus_powerline_font_osx
[powerline-git]: https://github.com/powerline/fonts
