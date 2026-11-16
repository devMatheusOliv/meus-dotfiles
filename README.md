cat > README.md <<'EOF'
# 🍎 meus-dotfiles

![Fedora](https://img.shields.io/badge/Fedora-45-51A2DA?style=flat&logo=fedora&logoColor=white)
![GNOME](https://img.shields.io/badge/GNOME-51-4A86CF?style=flat&logo=gnome&logoColor=white)
![Fish](https://img.shields.io/badge/shell-fish-4aae46?style=flat)

![Desktop](screenshots/desktop.png)

Meu setup de GNOME com visual estilo macOS, guardado pra restaurar em qualquer distro
(Fedora, CachyOS/Arch).

---

## ✨ O que tem aqui

- 🎨 **Tema:** MacTahoe-Dark (GTK), ícones WhiteSur, cursor Future-cyan
- 🧩 **Extensões:** Blur my Shell, Glidedock, Tiling Shell, Vitals, Caffeine, Weather O'Clock, Desktop Widgets e mais
- 🐟 **Terminal:** Ptyxis + Fish + Fastfetch
- 🎬 **Apps:** configs do MPV e GTK
- 🖼️ **Wallpapers** que eu uso

## 🚀 Instalar

```bash
git clone https://github.com/devMatheusOliv/meus-dotfiles
cd meus-dotfiles
./install.sh
```

O script faz **backup** do que já existe em `~/.config-backups/` antes de sobrescrever.

> ⚠️ Antes de rodar, instala o tema, os ícones e o cursor (eles não estão no repo, pesam muito):
> [MacTahoe GTK](https://github.com/vinceliuice/MacTahoe-gtk-theme) ·
> [WhiteSur icons](https://github.com/vinceliuice/WhiteSur-icon-theme) ·
> Future-cyan cursors

## 📁 Estrutura

| Pasta / arquivo | O que é |
|---|---|
| `install.sh` | instala tudo (wallpapers, configs, extensões, flatpaks, dconf) |
| `gnome-settings.dconf` | configurações do GNOME (tema, dock, atalhos, extensões) |
| `extensoes/` | extensões do GNOME Shell |
| `config/` | configs de apps (fastfetch, mpv, gtk, Ptyxis) |
| `fish/` | config do Fish |
| `wallpapers/` | papéis de parede |
| `flatpaks.txt` | lista de Flatpaks |
| `pacotes-fedora.txt` | pacotes instalados no Fedora (referência) |

## 🔄 Atualizar o backup

```bash
dconf dump / > gnome-settings.dconf
gnome-extensions list --enabled > extensoes-ativas.txt
flatpak list --app --columns=application > flatpaks.txt
git add . && git commit -m "atualiza dotfiles" && git push
```

## 📝 Notas

- O `dconf` aponta pro wallpaper em `/home/mat/.local/share/backgrounds/`. Se o usuário for outro, ajusta com `gsettings set org.gnome.desktop.background picture-uri ...`
- Nunca subir: `discord/`, `gh/`, `goa-1.0/`, `mozilla/` (tokens e dados pessoais).
EOF
