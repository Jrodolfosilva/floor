# FloorFlex – Landing Page

Recriação limpa (sem WordPress/Elementor) da LP `floorflex.com.br/lp/`, com UI/UX revisado e otimizada para performance.

## Estrutura

```
index.html      LP v1 – CTAs levam ao WhatsApp / formulário da página
v2/index.html   LP v2 – CTAs (.f-wa) abrem popup de 3 etapas → webhook n8n + WhatsApp
img/            Imagens WebP em 2 tamanhos (srcset)
fonts/          Montserrat e Roboto (woff2 variáveis, subset latin)
.htaccess       Cache longo + compressão (Apache)
```

## Configuração da v2 (n8n)

Em `v2/index.html`, no script do popup:

```js
const N8N_DOMAIN       = "https://SEU-DOMINIO-N8N.com.br";   // trocar pelo domínio real
const N8N_WEBHOOK_PATH = "/webhook/floorflex-orcamento";
```

Payload enviado (POST JSON): `prazo, metragem, compra, nome, telefone, cidade, mensagem, origem, pagina, dispositivo, data_envio, utm_*`.

## Deploy

Subir `index.html`, `v2/`, `img/`, `fonts/` e `.htaccess`. A v2 usa `../img` e `../fonts`, então deve ficar como subpasta da v1 (ex.: `/lp/` e `/lp/v2/`).
