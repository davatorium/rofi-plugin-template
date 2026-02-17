# Rofi plugin template

Template for creating rofi plugins.

Run rofi like this:

```bash
rofi -show myplugin -modi myplugin
```

## Compilation

### Installation

**Rofi-plugin-template** uses meson as the build system:

```bash
meson setup build
#meson compile -C build
meson install -C build
```
