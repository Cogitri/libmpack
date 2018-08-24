project(
  'libmapck',
  'c',
  version : '1.0.5',
  license : 'MIT',
)

inc = include_directories(
  '.',
  'src',
)

subdir('src')
subdir('test')

import('pkgconfig').generate(
  libraries : libmpack,
  version : '1.0.0',
  name : 'mpack',
  filebase : 'mpack',
  description : 'small binary serialization library implementing msgpack and msgpack-rpc formats',
)
