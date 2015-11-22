xing_sources = [
  'plugin.c',
  'gstxingmux.c',
]

gstxingmux = library('gstxingmux',
  xing_sources,
  c_args : core_args,
  include_directories : core_incs,
  dependencies : [gstbase_dep],
)
