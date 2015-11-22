asf_sources = [
  'gstasfdemux.c',
  'gstasf.c',
  'asfheaders.c',
  'asfpacket.c',
  'gstrtpasfdepay.c',
  'gstrtspwms.c',
]

gstasf = library('gstasf',
  asf_sources,
  c_args : core_args,
  include_directories : core_incs,
  dependencies : [gstbase_dep, gstrtp_dep, gstvideo_dep, gstaudio_dep, gsttag_dep],
)
