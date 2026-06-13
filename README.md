# Rastreador de Hábitos

Aplicativo web (PWA) para acompanhar hábitos diários e semanais: sequências, metas, taxa de conclusão, mapa de calor de 90 dias e sparklines. Funciona **100% offline** e guarda os dados no próprio dispositivo (sem servidor, sem cadastro).

## Como rodar localmente

É um site estático. Como o navegador bloqueia `file://` para alguns recursos, sirva por um servidor local:

```bash
python3 -m http.server 4599
```

Depois abra <http://localhost:4599/index.html>.

## Como usar no celular (instalar como app)

1. Publique no GitHub Pages (ou Netlify/Cloudflare Pages).
2. Abra a URL `https://...` no celular (Chrome no Android, Safari no iPhone).
3. Menu do navegador → **Adicionar à tela inicial**.

O app instala com ícone próprio, abre em tela cheia e funciona offline.

## Backup dos dados

Os dados ficam no armazenamento do navegador de **cada** dispositivo — não sincronizam entre aparelhos. Use os botões **Exportar** (baixa um `.json`) e **Importar** (restaura) para mover ou guardar uma cópia.

## Estrutura

- `index.html` — app completo (React + lógica, via Babel no navegador).
- `vendor/` — React, ReactDOM e Babel locais (uso offline).
- `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png` — PWA (instalação e cache offline).
