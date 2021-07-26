# Ansible Role: PageSpeed

Install PageSpeed module for Nginx (from source).
https://developers.google.com/speed/pagespeed/module

![PageSpeed Test](https://developers.google.com/speed/pagespeed/images/psi.png)

## Requirements

None.

## Role Variables

### Common packages:
```
pcre_version: pcre-8.44
zlib_version: zlib-1.2.11
openssl_version: openssl-1.1.1g
nginx_version: nginx-1.21.1
```
This list of packages are build from source. You can modify the nginx release (mainline, stable or legacy versions):

https://nginx.org/en/download.html

### Apache Incubator PageSpeed
https://www.modpagespeed.com/doc/release_notes
```
nps_version: 1.13.35.2
nps_release: stable
```
The version '1.14.36.1' does not support the variable `nps_release`, also I did not found compatible release of PSOL.

### Webserver:
```
website: domain.local
server_signature: TimeMachine
change_server_signature: no
```
You can overwrite the server signature. The default server signature will be '*server: nginx*'.

In adition you can modify the variable `nginx_configure` in order build or remove modules from nginx (see `defaults/main.yml`).

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  roles:
    - mariocorado.pagespeed
```

## License

MIT

## Author Information

This role was created in 2021 by Mario Corado.
