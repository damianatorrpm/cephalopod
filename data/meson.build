subdir('ui')

desktop_file = i18n.merge_file(
    input: 'pcmanfm.desktop.in',
    output: 'pcmanfm.desktop',
    type: 'desktop',
    po_dir: meson.source_root() / 'po',
    install: true,
    install_dir: get_option('prefix') / get_option('datadir') / 'applications'
)

desktop_file_pref = i18n.merge_file(
    input: 'pcmanfm-desktop-pref.desktop.in',
    output: 'pcmanfm-desktop-pref.desktop',
    type: 'desktop',
    po_dir: meson.source_root() / 'po',
    install: true,
    install_dir: get_option('prefix') / get_option('datadir') / 'applications'
)

desktop_utils = find_program('desktop-file-validate', required: false)
if desktop_utils.found()
    test('Validate desktop file', desktop_utils,
        args: [desktop_file, desktop_file_pref]
    )
endif

appstream_file = i18n.merge_file(
    input: 'cephalopod.appdata.xml.in',
    output: 'cephalopod.appdata.xml',
    po_dir: meson.source_root() / 'po',
    install: true,
    install_dir: get_option('prefix') / get_option('datadir') / 'appdata'
)

appstream_util = find_program('appstream-util', required: false)
if appstream_util.found()
    test('Validate appstream file', appstream_util,
        args: ['validate', appstream_file]
    )
endif

install_data('pcmanfm.conf',
    install_dir: get_option('prefix') / get_option('sysconfdir')
)

man_page = configure_file(
    input: 'pcmanfm.1.in',
    output: 'pcmanfm.1',
    configuration: version_conf_data
)

install_man(man_page)
