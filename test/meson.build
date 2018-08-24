subdir('deps')

t_sources = [
  'fixtures.c',
  'mpack.c',
]

cpp = meson.get_compiler('c')

libm_dep = cpp.find_library('libm')

test_exe = executable(
  'mpack',
  t_sources,
  include_directories : inc,
  dependencies: [ libmpack_dep, tap_dep, libm_dep ],
  install : false,
)

test(
  'test_mpack',
  test_exe,
)