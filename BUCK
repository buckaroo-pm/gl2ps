load('//:buckaroo_macros.bzl', 'buckaroo_deps_from_package')
load('//:subdir_glob.bzl', 'subdir_glob')

pkg_config_gl = \
  buckaroo_deps_from_package('github.com/buckaroo-pm/pkg-config-gl')

host_opengl = \
  buckaroo_deps_from_package('github.com/buckaroo-pm/host-opengl')

freeglut = \
  buckaroo_deps_from_package('github.com/buckaroo-pm/freeglut')

cxx_library(
  name = 'gl2ps',
  header_namespace = '',
  exported_headers = [
    'gl2ps.h',
  ],
  srcs = [
    'gl2ps.c',
  ],
  platform_deps = [
    ('linux.*', pkg_config_gl),
    ('macos.*', host_opengl),
  ],
  visibility = [
    'PUBLIC',
  ],
)

cxx_binary(
  name = 'test',
  srcs = [
    'gl2psTest.c',
  ],
  deps = freeglut + [
    ':gl2ps',
  ],
)
