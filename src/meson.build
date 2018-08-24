headers = [
	'conv.h',
	'core.h',
	'object.h',
	'rpc.h',
]

c_source=[
	'conv.c',
	'core.c',
	'object.c',
	'rpc.c'
]

# Combine all headers into mpack.h
concated_h = custom_target(
	'concated.h',
	input: headers,
	output: 'concated.h',
	command: [
		'cat',
		'@INPUT@',
	],
	capture: true,
)

# Remove all includes from mpack.h
mpack_h = custom_target(
	'mpack.h',
	input: concated_h,
	output: 'mpack.h',
	install: true,
	install_dir: get_option('includedir'),
	command: [
		'sed',
		'/#include/d',
		'@INPUT@',
	],
	capture: true,
)

# Merge all c files and mpack.h into mpack.c
mpack_c = custom_target(
	'mpack_c',
  input : [
	c_source,
	mpack_h,
  ],
  output : 'mpack.c',
  command : [
		'cat',
		'@INPUT@',
  ],
	capture: true,
)

libmpack = both_libraries(
  'mpack',
  mpack_c,
  version : '1.0.0',
  include_directories : inc,
  install : true,
)
