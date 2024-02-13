project(
  '{{cookiecutter.project_slug}}',
  'cpp',
  version : '{{cookiecutter.project_version}}',
  default_options : [
    'buildtype=release',
    'warning_level=3',
    'cpp_std=c++20',
    'b_ndebug=if-release'],
  meson_version : '>= 0.52.0')

add_global_arguments([
  '-DPACKAGE_NAME="' + meson.project_name() + '"',
  '-DPACKAGE_VERSION="' + meson.project_version() + '"'],
  language : 'cpp'
)

cpp = meson.get_compiler('cpp')
warning_flags = []
foreach cflag: [
  '-Wdouble-promotion',
  '-Wduplicated-cond',
  '-Wduplicated-branches',
  '-Wlogical-op',
  '-Wnull-dereference',
  '-Wrestrict',
  '-Wuseless-cast',
  '-Wshadow',
  '-Wformat=1']
    if cpp.has_argument(cflag)
      warning_flags += cflag
    endif
endforeach

inc = include_directories('include')

subdir('include')
subdir('src')

if get_option('tests')
  subdir('tests')
endif


if get_option('executable')
  {{ cookiecutter.project_slug }}_cpp_sources = files([
    'src/main.cpp'
  ])

  {{ cookiecutter.project_slug }}_exe = executable(
    '{{ cookiecutter.project_slug }}',
    {{ cookiecutter.project_slug }}_cpp_sources,
    cpp_args : warning_flags,
    include_directories : inc,
    link_with : [cppdev_lib],
  )
endif
