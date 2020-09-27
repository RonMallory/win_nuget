win_nuget
=========

Ansible role to install nuget.exe from nuget.org

Role Variables
--------------
```yaml
# variable defanitions

nuget.packagename     == name of the nuget package in nuget.org
nuget.source:         == source nuget location can be nuget.org or internal nuget proxy
nuget.version:        == Version of the package to be installed
nuget.policy:         == Trust status to nuget repo default 'Trusted'
nuget.install_path:   == destination path to install nuget.exe
path_var:             == System Path variable for nuget exe.  If modifying the destination path be sure to update the system path so you can utilize nuget on command line.
```

```yaml
# Default values
nuget:
  package_name: 'nuget.commandline'
  source: 'http://nuget.org/api/v2/'
  version: '5.7.0'
  policy: 'Trusted'
  install_path: 'c:\buildtools'
path_var: |
  {{ nuget.install_path }}\{{ nuget.package_name }}.{{ nuget.version }}\tools
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
---
- name: win_nuget default playbook
  hosts: all
  gather_facts: no
  tasks:
    - name: "Include win_oneget"
      include_role:
        name: "win_oneget"
...
  
```

License
-------

AGPL-3.0-or-later

Author Information
------------------

Name: Ron Mallory

Email: Ronnymallory@gmail.com

