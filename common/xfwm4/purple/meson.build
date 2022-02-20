xfwm_purple_assets = []
xfwm_purple_asset_files = []

foreach asset : xfwm_asset_names

  asset_filename = asset + '.png'

  if fs.exists(asset_filename)
    xfwm_purple_asset_files += meson.current_source_dir() / asset_filename
  else
    if not inkscape.found()
      error('Program \'inkscape\' not found')
    endif

    xfwm_purple_assets += custom_target(
      'xfwm-purple-' + asset,
      input : 'assets.svg',
      output : asset_filename,
      command : [
        inkscape,
        '--export-id-only',
        inkscape_ver.version_compare('>=1.0') ? '--export-filename=@OUTPUT@' : '--export-png=@OUTPUT@',
        '--export-id=' + asset,
        '--export-dpi=96',
        '@INPUT@'
      ],
      build_by_default : true
    )
  endif
endforeach
