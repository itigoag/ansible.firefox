# Ansible Role: firefox

[![Build Status](https://img.shields.io/travis/itigoag/ansible.firefox.svg?branch=master&style=popout-square)](https://travis-ci.org/itigoag/ansible.firefox) [![license](https://img.shields.io/github/license/mashape/apistatus.svg?style=popout-square)](https://sbaerlo.ch/licence) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-firefox-blue.svg?style=popout-square)](https://galaxy.ansible.com/itigoag/firefox) [![Ansible Role](https://img.shields.io/ansible/role/d/30128.svg?style=popout-square)](https://galaxy.ansible.com/itigoag/firefox)

## Description

Installs then Firefox on Windows devices and configures new Firefox [Policy Engine](https://github.com/mozilla/policy-templates/blob/master/README.md).

## Installation

```bash
ansible-galaxy install itigoag.firefox
```

## Requirements

To make it work it needs the Payton extension.

```bash
sudo pip install jmespath
```

## Role Variables

| Variable             | Default     | Comments (type)                                   |
| :---                 | :---        | :---                                              |
| firefox_install | true | Firefox installed or not installed |
| firefox_policies | | Standart Policies |
| firefox_policies_group | | Group Policies |
| firefox_policies_host | | Host Policies |

The exact configurations are Repositroy in the following: [Policy Templates](https://github.com/mozilla/policy-templates/blob/master/README.md)

### Examples Variables

```yml
firefox_policies:
  policies:
    DisableAppUpdate: true
    DisableBuiltinPDFViewer: true
    DisableDeveloperTools: true
    DisableFeedbackCommands: true
    DisableFirefoxStudies: true
    DisablePocket: true
    DisableTelemetry: true
    DontCheckDefaultBrowser: true
    InstallAddonsPermission:
      Default: false
    NoDefaultBookmarks: true
    OverrideFirstRunPage: ''
    OverridePostUpdatePage: ''
    OfferToSaveLogins: true
    Homepage:
      StartPage: homepage
      URL: about:newtab
```

## Dependencies

None

## Example Playbook

```yml
- hosts: all
  roles:
     - itigoag.firefox
```

## Changelog

### 1.1.0

* new default Settings

### 1.0.0

* inital commit

## Author

* [Simon Bärlocher](https://sbaerlocher.ch)
* [ITIGO AG](https://www.itigo.ch)

## License

This project is under the MIT License. See the [LICENSE](licence) file for the full license text.

## Copyright

(c) 2019, Simon Bärlocher
(c) 2019, ITIGO AG
