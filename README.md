Nginx http proxy
=================


Nginx proxy for other HTTP webserver

Role Variables
--------------

- `domains` - list of domains (required)
- `http_port` - default: 80
- `ssl` - provide SSL connection channel (default: False)
- `http_redirect` - if both above variable and this is set - provide :80->https redirect
- `cert` - public SSL certificate path 
- `cert_key` - private SSL certificate path
- `proxies` -  list of dictionaries:
    - `location` - path we want to proxy,
    - `host` - host of proxied service (defualts to `proxy_host`)
    - `port` - port to proxied service (defualts to `proxy_port`)
    - `remote_location` - HTTP path where we want to proxy (defaults to `.location`)
- `proxy_host` - defaults to `127.0.0.1`
- `proxy_port` - defaults to `8000`

Dependencies
------------

- [nginx_base](https://github.com/kkoralsky/ansible_nginx_base)

Example Playbook
----------------

    - hosts: servers
      roles:
        - { role: nginx_http_proxy, domains: [ example.com ] }

License
-------

BSD
