## Wildparrot DNS configurator

### Overview 
This playbook completes full(ish) configuration of the wildparrot external DNS server.

This includes the following config:

* IPtables firewall rules
* Wireguard VPN
* Bind DNS server

The playbook configures DNS records according to the vars file zones.yml - records can be added and the playbook run to add more records.

Keys for DNS updates and zone transfers are included in ansible-vault encrypted files, so don't forget to use the option `--ask-vault-pass` when executing the playbook.

### Possible improvements / limitations
* The whole configuration is very specific for the codyroad.online environment and not generalised in the slightest, this was intentional although could be seen as a limitation.
* Initial zone files are a default file within the serial baked in, at the time of build the number was correct, if the server had to be rebuilt these files would need an update. It would be better to templatise the zone files.
* Bind configs are also no particularly dynamic, be be better to templatise in the future.
