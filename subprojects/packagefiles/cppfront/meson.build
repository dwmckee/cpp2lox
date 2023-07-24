project('cppfront', 'cpp', default_options: ['cpp_std=c++20'])

cppfront = executable('cppfront', 'source/cppfront.cpp',
   override_options: ['optimization=2'])

meson.override_find_program('cppfront', cppfront)
cpp2_dep = declare_dependency(include_directories: 'include')
