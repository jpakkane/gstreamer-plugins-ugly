dvdpl_sources = [
  'gstdvdlpcmdec.c'
]

gstdvdlpcmdec = library('gstdvdlpcmdec',
  dvdpl_sources,
  c_args : core_args,
  include_directories : core_incs,
  dependencies : [gstbase_dep, gstaudio_dep],
)
