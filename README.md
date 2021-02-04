# Ansible Role: steamcmd

[![builds.sr.ht status](https://builds.sr.ht/~tleguern/ansible-steamcmd.svg)](https://builds.sr.ht/~tleguern/ansible-steamcmd?)

An Ansible role that installs steamcmd on a Linux server.

Automatic testing is provided using molecule's delegated driver and https://builds.sr.ht.

## Requirements

None.

## Role Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `steamcmd_download_url` | URL pointing to the steamcmd archive | `https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz` |
| `steamcmd_bin_path` | Installation directory of steamcmd, when `steamcmd_manual=True` | `/usr/local/games` |
| `steamcmd_lib_path` | Intermediate installation directory of steamcmd, when `steamcmd_manual=True` |
| `steamcmd_user` | User name for steamcmd | `steam` |
| `steamcmd_manual` | Prefer manual installation | `{{ __steamcmd_manual }}` |
| `steamcmd_required_packages` | Dependencies | `{{ __steamcmd_required_packages }}` |
| `steamcmd_package` | Name of package | `{{ __steamcmd_package }}` |
| `steamcmd_deb_mirror` | URL of an APT mirror | `{{ __steamcmd_deb_mirror }}` |
| `steamcmd_repositories` | APT repositories to enable | `{{ __steamcmd_repositories }}`

### Debian

| Variable | Default |
|----------|---------|
| `__steamcmd_manual` | `False` |
| `__steamcmd_package` | `steamcmd` |
| `__steamcmd_deb_mirror` | `https://deb.debian.org/debian/` |
| `__steamcmd_repositories` | `contrib non-free` |
| `__steamcmd_required_packages` | `lib32gcc1` |

### RedHat

| Variable | Default |
|----------|---------|
| `__steamcmd_manual` | `True` |
| `__steamcmd_required_packages` | `[ 'glibc.i686', 'libstdc++.i686' ]` |

### Ubuntu

| Variable | Default |
|----------|---------|

| Variable | Default |
|----------|---------|
| `__steamcmd_manual` | `False` |
| `__steamcmd_package` | `steamcmd` |
| `__steamcmd_deb_mirror` | `http://archive.ubuntu.com/ubuntu/` |
| `__steamcmd_repositories` | `multiverse` |
| `__steamcmd_required_packages` | `lib32gcc1` |

# Dependencies

None

# Example Playbook

```yaml
- hosts: game
  roles:
  - ansible-steamcmd
```

# License

```
The MIT License (MIT)

Copyright (c) 2018 Damien Plénard

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## Contributing

Either send [send GitHub pull requests](https://github.com/Aversiste/ansible-steamcmd) or [send patches on SourceHut](https://lists.sr.ht/~tleguern/misc).

# Author Information

Original work from [Damien Plénard](https://gitlab.com/dam0un/ansible-steamcmd) with adaptations from Tristan Le Guern.
