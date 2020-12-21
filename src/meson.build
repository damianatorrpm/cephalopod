add_project_arguments('-DPACKAGE_UI_DIR="' + get_option('prefix') / get_option('datadir') / 'pcmanfm/ui' + '"', language: 'c')
add_project_arguments('-DPACKAGE_DATA_DIR="' + get_option('prefix') / get_option('datadir') / 'pcmanfm' + '"', language: 'c')
add_project_arguments('-DPACKAGE_LOCALE_DIR="' + get_option('prefix') / get_option('localedir') + '"', language: 'c')
add_project_arguments('-DPACKAGE_MODULES_DIR="' + get_option('prefix') / get_option('libdir') / 'pcmanfm' + '"', language: 'c')
add_project_arguments('-DGETTEXT_PACKAGE="@0@"'.format(meson.project_name()), language:'c')

cc = meson.get_compiler('c')

pcmanfm_sources = [
    'pcmanfm.c',
    'app-config.c',
    'main-win.c',
    'tab-page.c',
    'desktop.c',
    'volume-manager.c',
    'pref.c',
    'single-inst.c',
    'connect-server.c'
]

pcmanfm_deps = [
    dependency('gthread-2.0'),
    dependency('gio-unix-2.0', version: '>= 2.28.0'),
    dependency('glib-2.0', version: '>= 2.28.0'),
    dependency('pango', version: '>= 1.20.0'),
    dependency('gtk+-3.0', version: '>= 3.22.0'),
    dependency('libfm', version: '>= 1.2.1'),
    dependency('libfm-gtk3', version: '>= 1.2.1'),
    dependency('x11'), 
    cc.find_library('m', required: false)
]

executable('pcmanfm', pcmanfm_sources,
    dependencies: pcmanfm_deps,
    install: true
)

install_headers('pcmanfm-modules.h')
