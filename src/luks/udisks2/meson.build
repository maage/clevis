audit = dependency('audit', version: '>=2.7.8', required: false)
udisks2 = dependency('udisks2', required: false)

if udisks2.found() and audit.found()
  autostartdir = join_paths(sysconfdir, 'xdg', 'autostart')

  configure_file(
    input: 'clevis-luks-udisks2.desktop.in',
    output: 'clevis-luks-udisks2.desktop',
    install_dir: autostartdir,
    configuration: data,
  )

  executable('clevis-luks-udisks2', 'clevis-luks-udisks2.c',
    dependencies: [udisks2, luksmeta, audit, jansson],
    install_dir: libexecdir,
    install: true,
  )
endif