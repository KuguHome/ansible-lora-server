This role installs https://www.loraserver.io/. It is based upon https://github.com/brocaar/loraserver-setup, but pulls all parts into one one role instead of having several roles in parallel.

```
roles:
- role: lora-server
  lora_appserver_public_host: "{{kugu_appserver_domain}}"
  lora_mqttserver: "tcp://{{vms['kugu-os-mosquitto'].ecs_ipaddress}}:1883"
```

Uninstall LoRa from machine:

```
roles:
- role: lora-server
  lora_uninstall: yes
  lora_networkserver_use: no
  lora_appserver_use: no
  lora_postgresql_use: no
```