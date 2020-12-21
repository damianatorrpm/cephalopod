version_conf_data = configuration_data()
version_conf_data.set('PACKAGE', meson.project_name())
version_conf_data.set('VERSION', meson.project_version())

configure_file(
    input: 'about.ui.in',
    output: 'about.ui',
    configuration: version_conf_data,
    install: true,
    install_dir: get_option('prefix') / get_option('datadir') / 'pcmanfm/ui'
)

install_data('autorun.ui',
    install_dir: get_option('prefix') / get_option('datadir') / 'pcmanfm/ui'
)

install_data('connect.ui',
    install_dir: get_option('prefix') / get_option('datadir') / 'pcmanfm/ui'
)

install_data('desktop-pref.ui',
    install_dir: get_option('prefix') / get_option('datadir') / 'pcmanfm/ui'
)

install_data('pref.ui',
    install_dir: get_option('prefix') / get_option('datadir') / 'pcmanfm/ui'
)
