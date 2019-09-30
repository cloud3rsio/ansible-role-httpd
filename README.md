cloud3rsio.httpd
=========

Install httpd.

Installation
------------

```bash
$ ansible-galaxy install cloud3rsio.httpd
```

Requirements
------------

Nothing.

Role Variables
--------------

| Key | Default Value | Type |
| ------------- | ------------- | ------------- |
| `httpd_ServerRoot` | `/etc/httpd` | String |
| `httpd_Listen` | `'0.0.0.0:80'` | String |
| `httpd_User` | `apache` | String |
| `httpd_Group` | `apache` | String |
| `httpd_ServerAdmin` | `root@localhost` | String |
| `httpd_ServerName` | `localhost` | String |
| `httpd_SuexecUser` | `apache` | String |
| `httpd_SuexecGroup` | `apache` | String |
| `httpd_DocumentRoot_Directory` | `/var/www/html` | String |
| `httpd_DocumentRoot_AllowOverride` | `All` | String |
| `httpd_DocumentRoot_Options` | `'MultiViews FollowSymLinks IncludesNoExec ExecCGI'` | String |
| `httpd_DocumentRoot_Require` | `'all granted'` | String |
| `httpd_DirectoryIndex` | `index.php index.html` | String |
| `httpd_Log_combined_Format` | `'%h %v:%p %l %u %t \"%r\" %>s %b \"%{Referer}i\" \"%{User-Agent}i\" %D \"%{X-Forwarded-For}i\"'` | String |
| `httpd_Log_combined_CustomLog` | `logs/access_log` | String |
| `httpd_EnableMMAP` | `'off'` | String |
| `httpd_EnableSendfile` | `'on'` | String |
| `httpd_IncludeOptional` | `'conf.d/*.conf'` | String |
| `httpd_ServerTokens` | `Prod` | String |
| `httpd_TraceEnable` | `'off'` | String |
| `httpd_KeepAlive_Status` | `'On'` | String |
| `httpd_KeepAlive_MaxRequests` | `100` | Int |
| `httpd_KeepAlive_Timeout` | `2` | Int |
| `httpd_mpm_select` | `event` | String |
| `httpd_mpm_prefork_StartServers` | `4` | Int |
| `httpd_mpm_prefork_MinSpareServers` | `4` | Int |
| `httpd_mpm_prefork_MaxSpareServers` | `32` | Int |
| `httpd_mpm_prefork_ServerLimit` | `64` | Int |
| `httpd_mpm_prefork_MaxRequestWorkers` | `64` | Int |
| `httpd_mpm_prefork_MaxRequestsPerChild` | `500` | Int |
| `httpd_mpm_event_StartServers` | `2` | Int |
| `httpd_mpm_event_MinSpareThreads` | `25` | Int |
| `httpd_mpm_event_MaxSpareThreads` | `50` | Int |
| `httpd_mpm_event_ThreadLimit` | `150` | Int |
| `httpd_mpm_event_ThreadsPerChild` | `100` | Int |
| `httpd_mpm_event_MaxRequestWorkers` | `500` | Int |
| `httpd_mpm_event_MaxConnectionsPerChild` | `10000` | Int |
| `httpd_ExtendedStatus` | `'On'` | String |
| `httpd_ExtendedStatusAddress` | `127.0.0.1:10080` | String |
| `httpd_use_phpfpm_socket` | Reference to [defaults/main.yml](defaults/main.yml) | Hash |
| `httpd_use_phpfpm_socket.enabled` | `yes` | Bool |
| `httpd_use_phpfpm_socket.proxy_url` | `balancer://php7.3.9` | String |
| `httpd_use_phpfpm_socket.balancer_member_url` | `unix:/var/run/php-fpm-7.3.9.sock|fcgi://php7.3.9` | String |
| `httpd_use_https` | `no` | Bool |
| `httpd_https_port` | `443` | String |
| `httpd_https_SSLCertificateFile` | `/etc/pki/tls/certs/localhost.crt` | String |
| `httpd_https_SSLCertificateKeyFile` | `/etc/pki/tls/private/localhost.key` | String |
| `httpd_https_SSLCACertificateFile` | `/etc/pki/tls/certs/ca-bundle.crt` | String |

Dependencies
------------

Nothing.

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: cloud3rsio.httpd
```

License
-------

[MIT](LICENSE)

Author Information
------------------

- youyo
