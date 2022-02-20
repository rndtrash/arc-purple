if 'light' in get_option('variants') or 'lighter' in get_option('variants')
  subdir('light')
endif

if 'dark' in get_option('variants') or 'darker' in get_option('variants')
  subdir('dark')
endif

if 'purple' in get_option('variants')
  subdir('purple')
endif

foreach variant : get_option('variants')
  if variant == 'light' or variant == 'lighter'
    themerc = 'light/gtk.css'
  elif variant == 'dark' or variant == 'darker'
    themerc = 'dark/gtk.css'
  elif variant == 'purple'
    themerc = 'purple/gtk.css'
  endif

  install_data(
    themerc,
    install_dir : prefix / install_dir.get(variant) / common_dirs.get('xfce-notify')
  )
endforeach
