# Rofi plugin template

Template for creating rofi plugins.

To run this you need an up to date checkout of rofi git installed.

Run rofi like:

```bash
    rofi -show myplugin -modi myplugin 
```

## Compilation

### Dependencies

| Dependency | Version         |
|------------|-----------------|
| rofi 	     | 1.4 (or git)	   |

### Installation

**Rofi-plugin-template** uses autotools as build system. If installing from git, the following steps should install it:

```bash
$ autoreconf -i
$ mkdir build
$ cd build/
$ ../configure
$ make
$ make install
```
