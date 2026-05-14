# Spy Projects — Checklist & Tracker

App single-page para gerenciar projetos de spy de anúncios e ofertas. 100% client-side, dados ficam no `localStorage` do navegador (com sync opcional via GitHub Gist).

## Features

- 📋 **Múltiplos projetos** com checklist customizável por template
- 📑 **Templates múltiplos** — crie checklists diferentes (spy rápido, completo, etc.)
- 🏷️ **Tags** com filtro na sidebar
- ⏱ **Deadline** por projeto com alertas visuais (verde / amarelo / vermelho)
- 📎 **Anexos de imagem** por item (paste, upload, redimensionado automático)
- 📝 **Notas** por item e por projeto
- 🔗 **Links e referências** por projeto
- 📜 **Timeline** de atividades (auto-log de checks, edits, removes)
- ⚡ **Modo "Rotina diária"** — todas as tarefas pendentes dos projetos ativos numa lista só
- 🔔 **Lembretes do navegador** com horário configurável
- ☁️ **Sync via GitHub Gist** — backup privado e acesso de qualquer máquina
- ⌨️ **Atalhos de teclado** (N, /, D, T, ?, Esc, Ctrl+S, ↑↓)
- 📱 **PWA** — instalável como app no desktop/celular, funciona offline
- 🌓 **Tema claro/escuro**
- ⬇⬆ **Export/Import JSON** pra backup local

## Como usar

Abra o `index.html` no navegador, ou hospede no GitHub Pages (instruções abaixo).

### Atalhos
| Tecla | Ação |
|-------|------|
| `N` | Novo projeto |
| `/` | Buscar |
| `D` | Alternar entre Projetos / Rotina diária |
| `T` | Templates |
| `,` | Configurações |
| `?` | Ver atalhos |
| `Ctrl+S` | Sync para Gist |
| `↑` `↓` | Navegar projetos |
| `Esc` | Fechar modal |

### Sync via GitHub Gist
1. Crie um Personal Access Token em https://github.com/settings/tokens/new com escopo `gist`
2. No app, clique no botão ☁️ no rodapé da sidebar
3. Cole o token e clique "Enviar pro Gist" — vai criar um gist privado e mostrar o ID
4. Use o mesmo token + gist ID em outra máquina pra puxar os dados
5. Ative "auto-sync" pra salvar automaticamente após cada mudança (debounce 5s)

### Hospedar no GitHub Pages
1. Crie um repositório novo no GitHub (ex.: `spy-checklist`)
2. Faça upload de todos os arquivos deste diretório
3. Settings → Pages → Branch: `main`, pasta `/ (root)`
4. Em ~1 min está disponível em `https://<seu-user>.github.io/<repo>/`

## Arquivos

- `index.html` — app principal (HTML + CSS + JS inline)
- `manifest.json` — manifest do PWA
- `sw.js` — service worker (cache offline)
- `icon.svg` — ícone do app

## Privacidade

Os dados ficam **apenas no seu navegador**. Nada é enviado pra servidor, exceto se você ativar a sync via Gist (e mesmo nesse caso, vai pro **seu** Gist privado no **seu** GitHub).

Anexos de imagem são salvos como base64 no `localStorage` (limite ~5-10MB total dependendo do navegador). Faça backups regulares via Exportar.
