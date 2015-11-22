project('gstreamer-plugins-ugly', 'c', version : '1.4.5',
  default_options : ['c_std=gnu99', 'warning_level=1'])

version_str = meson.project_version()
varr = version_str.split('.')
version_major = varr[0]
version_minor = varr[1]
version_micro = varr[2]
version_nano = 1
api_version = '1.0'

cc = meson.get_compiler('c')
cdata = configuration_data()
check_headers = [
  ['HAVE_DLFCN_H', 'dlfcn.h'],
  ['HAVE_INTTYPES_H', 'inttypes.h'],
  ['HAVE_MALLOC_H', 'malloc.h'],
  ['HAVE_MEMORY_H', 'memory.h'],
  ['HAVE_STDINT_H', 'stdint.h'],
  ['HAVE_STDLIB_H', 'stdlib.h'],
  ['HAVE_STRINGS_H', 'strings.h'],
  ['HAVE_STRING_H', 'string.h'],
  ['HAVE_SYS_STAT_H', 'sys/stat.h'],
  ['HAVE_SYS_TYPES_H', 'sys/types.h'],
  ['HAVE_UNISTD_H', 'unistd.h'],
  ['HAVE_WINSOCK2_H', 'winsock2.h'],
]

foreach h : check_headers
  if cc.has_header(h.get(1))
    cdata.set(h.get(0), 1)
  endif
endforeach

check_functions = [
# check token HAVE_A52DEC
# check token HAVE_AMRNB
# check token HAVE_AMRWB
# check token HAVE_CDIO
# check token HAVE_CFLOCALECOPYCURRENT
# check token HAVE_CFPREFERENCESCOPYAPPVALUE
# check token HAVE_CPU_ALPHA
# check token HAVE_CPU_ARM
# check token HAVE_CPU_CRIS
# check token HAVE_CPU_CRISV32
# check token HAVE_CPU_HPPA
# check token HAVE_CPU_I386
# check token HAVE_CPU_IA64
# check token HAVE_CPU_M68K
# check token HAVE_CPU_MIPS
# check token HAVE_CPU_PPC
# check token HAVE_CPU_PPC64
# check token HAVE_CPU_S390
# check token HAVE_CPU_SPARC
# check token HAVE_CPU_X86_64
  ['HAVE_DCGETTEXT', 'dcgettext', '#include<libintl.h>'],
# check token HAVE_DOWHILE_MACROS
# check token HAVE_DVDREAD
# check token HAVE_EXPERIMENTAL
# check token HAVE_EXTERNAL
# check token HAVE_FUNC
# check token HAVE_FUNCTION
# check token HAVE_GETTEXT
# check token HAVE_ICONV
# check token HAVE_LAME
# check token HAVE_MAD
# check token HAVE_MPEG2DEC
# check token HAVE_OPENCORE_AMRNB_0_1_3_OR_LATER
# check token HAVE_OPENCORE_AMRWB_0_1_3_OR_LATER
# check token HAVE_ORC
# check token HAVE_PRETTY_FUNCTION
# check token HAVE_RDTSC
# check token HAVE_SIDPLAY
# check token HAVE_TWOLAME
# check token HAVE_VALGRIND
# check token HAVE_X264
]

foreach f : check_functions
  if cc.has_function(f.get(1), prefix : f.get(2))
    cdata.set(f.get(0), 1)
  endif
endforeach

cdata.set('SIZEOF_CHAR', cc.sizeof('char'))
cdata.set('SIZEOF_INT', cc.sizeof('int'))
cdata.set('SIZEOF_LONG', cc.sizeof('long'))
cdata.set('SIZEOF_SHORT', cc.sizeof('short'))
cdata.set('SIZEOF_VOIDP', cc.sizeof('void*'))

# FIXMES
cdata.set('VERSION', '"@0@"'.format(version_str))
cdata.set('DEFAULT_VIDEOSRC', '"FIXME"')
cdata.set('PACKAGE', '"FIXME"')
cdata.set('PACKAGE_NAME', '"FIXME"')
cdata.set('GETTEXT_PACKAGE', '"FIXME"')
cdata.set('GST_PACKAGE_NAME', '"FIXME"')
cdata.set('GST_PACKAGE_ORIGIN', '"FIXME"')
cdata.set('GST_LICENSE', '"FIXME"')
cdata.set('LIBDIR', '"FIXME"')

# Mandatory GST deps
gst_dep = dependency('gstreamer-1.0')
gstapp_dep = dependency('gstreamer-app-1.0')
gstvideo_dep = dependency('gstreamer-video-1.0')
gstpbutils_dep = dependency('gstreamer-pbutils-1.0')
gsttag_dep = dependency('gstreamer-tag-1.0')
gstfft_dep = dependency('gstreamer-fft-1.0')
gstaudio_dep = dependency('gstreamer-audio-1.0')
gstbase_dep = dependency('gstreamer-base-1.0')
gstriff_dep = dependency('gstreamer-riff-1.0')
gstrtp_dep = dependency('gstreamer-rtp-1.0')
gstnet_dep = dependency('gstreamer-net-1.0')
gstsdp_dep = dependency('gstreamer-sdp-1.0')
gstrtsp_dep = dependency('gstreamer-rtsp-1.0')
gstcheck_dep = dependency('gstreamer-check-1.0')
gstcontroller_dep = dependency('gstreamer-controller-1.0')

orc_dep = dependency('orc-0.4')
zlib_dep = dependency('zlib')
gio_dep = dependency('gio-2.0')
#gl_dep = dependency('gl')

if orc_dep.found()
  cdata.set('HAVE_ORC', 1)
endif

configure_file(input : 'config.h.in',
  output : 'config.h',
  configuration : cdata)

core_args = ['-DHAVE_CONFIG_H']
core_incs = include_directories('.', 'gst-libs')

#subdir('gst')
#subdir('ext')
