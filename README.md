# Dotfiles i7 — SwayFX sur Fedora 44

Setup SwayFX pour desktop i7 avec double écran ASUS 2560×1440@144Hz + Samsung 1080p portrait, clavier AZERTY fr oss.

Adaptations vs [dotfiles-x1](https://github.com/melectronvolt/dotfiles-x1) :
- Pas de batterie dans Waybar
- Pas d'auto-power-profile (PC fixe)
- Pas de touchpad
- Configuration multi-écrans : workspaces 1-5 sur DP-1, 6-10 sur HDMI-A-1
- Waybar sur DP-1 uniquement
- Bluetooth et réseau dans le tray via blueman-applet et nm-applet

## Spécificités AZERTY

Sway attend les **keysyms** des touches, pas les labels. Sur AZERTY fr, la touche "1" sans Shift produit `&`, pas `1`. Les binds de workspace doivent donc cibler les symboles AZERTY :

| Workspace | Bind |
|---|---|
| 1 | `$mod+ampersand` (touche 1) |
| 2 | `$mod+eacute` (touche 2) |
| 3 | `$mod+quotedbl` (touche 3) |
| 4 | `$mod+apostrophe` (touche 4) |
| 5 | `$mod+parenleft` (touche 5) |
| 6 | `$mod+minus` (touche 6) |
| 7 | `$mod+egrave` (touche 7) |
| 8 | `$mod+underscore` (touche 8) |
| 9 | `$mod+ccedilla` (touche 9) |
| 10 | `$mod+agrave` (touche 0) |

Le scratchpad est déplacé de `$mod+minus` (qui est maintenant workspace 6) vers `$mod+less` (touche `<>` à gauche du W).

Les autres binds (lettres, flèches) utilisent `--to-code` pour rester layout-indépendants.

## Installation

Voir le [README du repo x1](https://github.com/melectronvolt/dotfiles-x1) pour les étapes de base. Spécifique desktop :

```bash
# Outputs : adapter selon tes écrans
swaymsg -t get_outputs   # donne les noms réels
```

## À venir

- Logid pour MX Master 4
- Portage du script toggle_ecran.py (Mutter → swaymsg)
- Looking Glass pour VM Win11 GPU passthrough
