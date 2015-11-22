real_sources = [
  'rademux.c',
  'rmdemux.c',
  'rmutils.c',
  'rdtdepay.c',
  'rdtmanager.c',
  'rtspreal.c',
  'realhash.c',
  'asmrules.c',
  'rdtjitterbuffer.c',
  'gstrdtbuffer.c',
  'pnmsrc.c',
  'realmedia.c'
]

gstrmdemux = library('gstrmdemux',
  real_sources,
  c_args : core_args,
  include_directories : core_incs,
  dependencies : [gstbase_dep, gstrtsp_dep, gstsdp_dep, gstpbutils_dep],
)
