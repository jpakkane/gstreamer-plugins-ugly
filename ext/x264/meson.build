x264_sources = [
  'gstx264enc.c',
]

gstx264 = library('gstx264',
  x264_sources,
  c_args : core_args,
  include_directories : core_incs,
  dependencies : [gstbase_dep, gstvideo_dep, gstpbutils_dep],
)
