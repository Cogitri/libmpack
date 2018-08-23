mpack_h_in = custom_target(
  'mpack.h.in',
  input : [
	'conv.h',
	'core.c',
	'object.h',
	'rpc.h',
  ],
  output : 'mpack.h.in',
  command : [
	'cat',
	'@INPUT@',
  ],
  capture : true,
)

mpack_h = custom_target(
  'mpack.h',
  input : mpack_h_in,
  command : [
	'sed',
	'/^#include "/d',
	'@INPUT@',
  ],
  output : 'mpack.h',
  capture : true,
  install : true,
  install_dir : get_option('includedir'),
)


mpack_c_in = custom_target('mpack_c_in',
  input : [
	'conv.c',
	'core.c',
	'mpack.c',
	'object.c',
	'rpc.c',
	mpack_h,
  ],
  output : 'mpack.c.in',
  command : [
	'cat',
	'@INPUT@',
  ],
  capture : true,
)

mpack_c = custom_target('mpack_c',
  input : [
	mpack_c_in,
  ],
  output : 'mpack.c',
  command : [
	'sed',
	'/^#include "/d',
	'@INPUT@',
  ],
  capture : true,
)

libmpack = both_libraries(
  'mpack',
  'mpack.c',
  version : '1.0.0',
  include_directories : inc,
  install : true,
)
