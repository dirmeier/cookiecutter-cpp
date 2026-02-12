gtest_dep = dependency(
  'gtest',
  main : true,
  required : true
)

cppdev_test_cpp_sources = files([
  'test.cpp'
])

cppdev_test = executable(
  'test_{{ cookiecutter.project_slug }}',
  cppdev_test_cpp_sources,
  cpp_args : warning_flags,
  dependencies : [gtest_dep],
  install : false,
  include_directories : inc,
  link_with : [cppdev_lib],
)

test('{{ cookiecutter.project_slug }} test', cppdev_test)
