# Ansible Role: Helpy
Ansible role to setup Helpy.

## Requirements
* Debian 8 "Jessie"
* Ansible 2.3.0

## Role Variables
```yaml
---
passenger:
  root: /usr/lib/ruby/vendor_ruby/phusion_passenger/locations.ini
  ruby: /home/rails/.rvm/gems/ruby-2.2.1/wrappers/ruby

postgres:
  dbname: helpy_production
  username: rails
  password: password

nginx: 
  server_name: helpy.mydomainname.com

  ssl_key_file: ~
  ssl_cert_file: ~
  ssl_key_path: /etc/nginx/ssl/helpy.key
  ssl_cert_path: /etc/nginx/ssl/helpy.crt

rvm:
  url: https://get.rvm.io
  temp_installer_path: /tmp/rvm-installer.sh
  root: /home/rails/.rvm
  ruby_version: 2.2.1
  init_script: /etc/profile.d/rvm.sh
  auto_update_rvm: true
  mypassword: rails
```

## Example Playbook
```yaml
---
- hosts: helpy
  remote_user: rails
  become: yes
  become_method: sudo
  roles:
    - helpy
```

## License
MIT License. See the [LICENSE file](LICENSE) for details.
