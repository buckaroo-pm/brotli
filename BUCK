compiler_flags = [
  '--pedantic-errors',
  '-Wall',
  '-Wconversion',
  '-Werror',
  '-Wextra',
  '-Wlong-long',
  '-Wmissing-declarations',
  '-Wmissing-prototypes',
  '-Wno-strict-aliasing',
  '-Wshadow',
  '-Wsign-compare',
]

cxx_library(
  name = 'common',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('c/common', '*.h'),
  ]),
  headers = subdir_glob([
    ('c/include', 'brotli/*.h'),
  ]),
  srcs = glob([
    'c/common/*.c',
  ]),
  compiler_flags = compiler_flags,
)

cxx_library(
  name = 'dec',
  header_namespace = '',
  headers = subdir_glob([
    ('c/include', 'brotli/*.h'),
    ('c/dec', '*.h'),
  ]),
  srcs = glob([
    'c/dec/*.c',
  ]),
  compiler_flags = compiler_flags,
)

cxx_library(
  name = 'enc',
  header_namespace = '',
  headers = subdir_glob([
    ('c/include', 'brotli/*.h'),
    ('c/enc', '*.h'),
  ]),
  srcs = glob([
    'c/enc/*.c',
  ]),
  compiler_flags = compiler_flags,
)

prebuilt_cxx_library(
  name = 'brotli',
  header_only = True,
  header_namespace = 'brotli',
  exported_headers = subdir_glob([
    ('c/include/brotli', '*.h'),
  ]),
  deps = [
    ':common',
    ':enc',
    ':dec',
  ],
  visibility = [
    'PUBLIC',
  ],
)
