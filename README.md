# Update Cloudflare DNS

Este script Bash atualiza dinamicamente registros DNS na Cloudflare com base no IP atual.

## Recursos

- Suporte a múltiplos domínios e registros DNS.
- Detecção automática de IP (interno ou externo).
- Atualização inteligente (somente se o IP ou configuração mudarem).
- Suporte a proxy da Cloudflare.
- Notificação via Telegram (opcional).

## Requisitos

- Bash
- cURL
- jq (para manipulação de JSON)

## Configuração

O arquivo `update-cloudflare-dns.conf` deve conter:

```ini
what_ip="external"
dns_record="ddns1.example.com, ddns2.example.com"
zoneid="SEU_ZONE_ID"
cloudflare_zone_api_token="SEU_API_TOKEN"
proxied="false"
ttl=1
notify_me_telegram="no"
telegram_chat_id="SEU_CHAT_ID"
telegram_bot_API_Token="SEU_BOT_TOKEN"
```

## Uso

Execute o script:

```sh
./update-cloudflare-dns.sh
```

Para rodar automaticamente, adicione ao crontab:

```sh
crontab -e
```

Adicione a linha:

```sh
*/5 * * * * /caminho/para/update-cloudflare-dns.sh
```

Isso atualizará os registros a cada 5 minutos.

## Licença

Este projeto é distribuído sob a MIT License.
