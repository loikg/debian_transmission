Role Name
=========

This a simple role for install [transmission-daemon](https://transmissionbt.com/) on debian and deriative.

Requirements
------------

None

Role Variables
--------------

This is all the variables and theire default values allowing you to tweak you transmission-daemon installation. Those variable are the same of the regular setting.json of transmission-daemon. You can find the documentation [here](https://github.com/transmission/transmission/wiki/Editing-Configuration-Files).

```
td_alt_speed_down: 50
td_alt_speed_enabled: 'false'
td_alt_speed_time_begin: 540
td_alt_speed_time_day: 127
td_alt_speed_time_enabled: 'false'
td_alt_speed_time_end: 1020
td_alt_speed_up: 50
td_bind_address_ipv4: '0.0.0.0'
td_bind_address_ipv6: '::'
td_blocklist_enabled: 'false'
td_blocklist_url: 'http://www.example.com/blocklist'
td_cache_size_mb: 4
td_dht_enabled: 'true'
td_download_dir: '/var/lib/transmission-daemon/downloads'
td_download_limit: 100
td_download_limit_enabled: 0
td_download_queue_enabled: 'true'
td_download_queue_size: 5
td_encryption: 1
td_idle_seeding_limit: 30
td_idle_seeding_limit_enabled: 'false'
td_incomplete_dir: '/var/lib/transmission-daemon/Downloads'
td_incomplete_dir_enabled: 'false'
td_lpd_enabled: 'false'
td_max_peers_global: 200
td_message_level: 1
td_peer_congestion_algorithm: ''
td_peer_id_ttl_hours: 6
td_peer_limit_global: 200
td_peer_limit_per_torrent: 50
td_peer_port: 51413
td_peer_port_random_high: 65535
td_peer_port_random_low: 49152
td_peer_port_random_on_start: 'false'
td_peer_socket_tos: 'default'
td_pex_enabled: 'true'
td_port_forwarding_enabled: 'false'
td_preallocation: 1
td_prefetch_enabled: 1
td_queue_stalled_enabled: 'true'
td_queue_stalled_minutes: 30
td_ratio_limit: 2
td_ratio_limit_enabled: 'false'
td_rename_partial_files: 'true'
td_rpc_authentication_required: 'true'
td_rpc_bind_address: '0.0.0.0'
td_rpc_enabled: 'true'
td_rpc_password: '{b1b09a49fdafce6f68b61f786dfe0f9b98c34573/vzJCs3P'
td_rpc_port: 9091
td_rpc_url: '/transmission/'
td_rpc_username: 'transmission'
td_rpc_whitelist: '127.0.0.1'
td_rpc_whitelist_enabled: 'true'
td_scrape_paused_torrents_enabled: 'true'
td_script_torrent_done_enabled: 'false'
td_script_torrent_done_filename: ''
td_seed_queue_enabled: 'false'
td_seed_queue_size: 10
td_speed_limit_down: 100
td_speed_limit_down_enabled: 'false'
td_speed_limit_up: 100
td_speed_limit_up_enabled: 'false'
td_start_added_torrents: 'true'
td_trash_original_torrent_files: 'false'
td_umask: 18
td_upload_limit: 100
td_upload_limit_enabled: 0
td_upload_slots_per_torrent: 14
td_utp_enabled: 'true'
```

Dependencies
------------

None

Example Playbook
----------------

```
- hosts: all
  become: yes
  become_method: su

  vars:
    username: 'downloader'
    password: 'password'

  roles:
    - role: debian_transmission
      td_rpc_username: "{{username}}"
      td_rpc_password: "{{password}}"

```

License
-------

The Unlicensed