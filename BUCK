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
    ('common', '*.h'),
  ]),
  headers = subdir_glob([
    ('include', 'brotli/*.h'),
  ]),
  srcs = glob([
    'common/*.c',
  ]),
  compiler_flags = compiler_flags,
)

cxx_library(
  name = 'dec',
  header_namespace = '',
  headers = subdir_glob([
    ('include', 'brotli/*.h'),
    ('dec', '*.h'),
  ]),
  srcs = glob([
    'dec/*.c',
  ]),
  compiler_flags = compiler_flags,
)

cxx_library(
  name = 'enc',
  header_namespace = '',
  headers = subdir_glob([
    ('include', 'brotli/*.h'),
    ('enc', '*.h'),
  ]),
  srcs = glob([
    'enc/*.c',
  ]),
  compiler_flags = compiler_flags,
)

prebuilt_cxx_library(
  name = 'brotli',
  header_only = True,
  header_namespace = 'brotli',
  exported_headers = subdir_glob([
    ('include/brotli', '*.h'),
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
