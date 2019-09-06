load('//:subdir_glob.bzl', 'subdir_glob')

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
  deps = [
    ':common',
  ],
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
  deps = [
    ':common',
  ],
)

prebuilt_cxx_library(
  name = 'brotli',
  header_only = True,
  header_namespace = 'brotli',
  exported_headers = subdir_glob([
    ('include/brotli', '*.h'),
  ]),
  exported_deps = [
    ':common',
    ':enc',
    ':dec',
  ],
  visibility = [
    'PUBLIC',
  ],
)
