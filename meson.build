project(
  'rofi-plugin-template',
  'c',
  version : '0.0.1',
  default_options : [
    'warning_level=3', # enables -Wall -Wextra
#    'werror=true',
    'strip=true',
    'c_std=gnu11'
  ]
)

# -------------------------------------------------
# Dependencies (equivalent to PKG_CHECK_MODULES)
# -------------------------------------------------
glib_dep = dependency(
  ['glib-2.0', 'gio-unix-2.0', 'gmodule-2.0'],
  version : '>= 2.40',
  required : true
)

rofi_dep = dependency('rofi', required : true)

# -------------------------------------------------
# Get Rofi plugin directory from pkg-config
# Equivalent to:
# ROFI_PLUGINS_DIR=`pkg-config --variable=pluginsdir rofi`
# -------------------------------------------------
rofi_plugins_dir = rofi_dep.get_variable(
  pkgconfig : 'pluginsdir'
)

# -------------------------------------------------
# Compiler flags (equivalent to AM_CFLAGS)
# -------------------------------------------------
add_project_arguments([
  '-Wparentheses',
  '-Winline',
  '-pedantic',
  '-Wunreachable-code'
], language : 'c')

# -------------------------------------------------
# Build plugin module
# Equivalent to:
# pkglib_LTLIBRARIES = myplugin.la
# myplugin_la_LDFLAGS = -module -avoid-version
# -------------------------------------------------
shared_module(
  'myplugin',
  sources : ['src/myplugin.c'],
  dependencies : [glib_dep, rofi_dep],
  install : true,
  install_dir : rofi_plugins_dir,
  name_prefix : '',      # avoid libmyplugin.so
#  soversion : '',        # avoid versioned .so
)
