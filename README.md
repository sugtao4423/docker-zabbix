# docker-zabbix
Zabbix の Docker Compose

## docker-compose.override.yml
Example

```yml
services:
  zabbix-agent:
    volumes:
      - ./agent.conf:/etc/zabbix/zabbix_agentd.d/agent.conf:ro
    logging:
      options:
        max-size: 1m
        max-file: '3'

  zabbix-server:
    environment:
      - ZBX_TIMEOUT=10
    logging:
      options:
        max-size: 1m
        max-file: '3'

  zabbix-web-nginx-mysql:
    logging:
      options:
        max-size: 1m
        max-file: '3'
```
