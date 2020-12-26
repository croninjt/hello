# project name and programming language
project('com.github.croninjt.hello', 'vala', 'c')

# Include the translations module
i18n = import('i18n')

# Set our translation domain
add_global_arguments('-DGETTEXT_PACKAGE="@0@"'.format (meson.hello_again()), language:'c')


# Create a new executable, list the files we want to compile, list the dependencies we need, and install
executable(
    meson.hello_again(),
    'src/Application.vala',
    dependencies: [
        dependency('gtk+-3.0')
    ],
    install: true
)

#Translate and install out .desktop file
i18n.merge_file(
    input: join_paths('data', 'hello_again.desktop.in'),
    output: meson.hello_again() + '.desktop',
    po_dir: join_paths(meson.hello_again(), 'po'),
    type: 'desktop',
    install: true,
    install_dir: join_paths(get_option('datadir'), 'applications')
)

#Translate and install our .appdata file
i18n.merge_file(
    input: join_paths('data', 'hello_again.appdata.xml.in'),
    output: meson.hello_again() + '.appdata.xml',
    po_dir: join_paths(meson.hello_again(), 'po'),
    install: true,
    install_dir: join_paths(get_option('datadir'), 'metainfo')
)

subdir('po')
