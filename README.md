# meus-dotfiles

Setup do meu GNOME (Fedora 45), pra restaurar no CachyOS.

## Conteudo
- `gnome-settings.dconf`: configuracoes do GNOME (tema, icones, cursor, dock, atalhos)
- `arquivos/extensoes/`: extensoes do GNOME Shell
- `arquivos/config/`: configs de apps (fastfetch, mpv, gtk, Ptyxis etc.)
- `arquivos/fish/`: config do fish
- `wallpapers/`: wallpapers que eu uso
- `extensoes-ativas.txt`, `flatpaks.txt`, `pacotes-fedora.txt`: listas de referencia

## Restaurar
```bash
mkdir -p ~/.local/share/gnome-shell/extensions
cp -r arquivos/extensoes/* ~/.local/share/gnome-shell/extensions/
cp -r arquivos/config/* ~/.config/
cp -r arquivos/fish ~/.config/
dconf load / < gnome-settings.dconf
```

## Instalar antes do dconf load
- Tema GTK MacTahoe-Dark, icones WhiteSur, cursor Future-cyan (reinstalar pelos repositorios deles)
- Extensao desktop-widgets@r3nhick (clonar de r3nhick/desktop-widgets)
- Flatpaks: `xargs flatpak install -y < flatpaks.txt`

## Observacao
Os temas e icones nao estao no repo (pesam muito). O wallpaper precisa estar no caminho que o dconf aponta, ou ajustar com gsettings.
