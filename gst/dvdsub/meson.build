dvdsub_sources = [
  'gstdvdsubdec.c',
  'gstdvdsubparse.c',
]

gstdvdsub = library('gstdvdsub',
  dvdsub_sources,
  c_args : core_args,
  include_directories : core_incs,
  dependencies : [gstbase_dep, gstvideo_dep],
)
