# lxd-functions

[![Build Status](https://drone.osshelp.ru/api/badges/ansible/lxd-functions/status.svg)](https://drone.osshelp.ru/ansible/lxd-functions)

Ansible role for LXHelper and lxd-functions library. Optionally can install required packages and python modules to perform testinfra tests of deployed containers.

## Usage example

```yaml
  roles:
    - role: lxd-functions,
      setup_testinfra: true
```

## Available parameters

### Main

| Param | Default | Description |
| -------- | -------- | -------- |
| `setup_testinfra` | `false` | Installs the required python modules for testing containers via Testinfra |

## Useful links

- [LXHelper documentation](https://github.com/OSSHelp/lxhelper)
- [deploy-functions library](https://github.com/OSSHelp/deploy-functions)

## TODO

- improve working with sha256: must be read from url, like in [ansible-drone](https://gitea.osshelp.ru/infra/ansible-drone/src/branch/devel/tasks/main.yml#L37):

```yaml
download_checksums: "https://oss.help/builds/drone/SHA256SUMS"
```

```yaml
- name: download binary
  get_url:
    url: "{{ download_url }}"
    checksum: "sha256:{{ download_checksums }}"
    dest: "{{ binary_dir }}/drone-server"
    mode: 0755
  notify: restart_drone
```

- remove redmine step ignore.

## License

GPL3

## Author

OSSHelp Team, see <https://oss.help>
