tap_sources = [
    'tap.c',
    'tap.h',
]

tap_lib = shared_library(
    'tap',
    tap_sources,
)

tap_dep = declare_dependency(
    link_with: tap_lib,
    include_directories: include_directories('.'),
)