project('cpp2lox',
 'cpp',
 default_options : ['cpp_std=c++20'])

cpp2_dep = dependency('cpp2')

cppfront = find_program('cppfront')

g = generator(cppfront,
  output: '@BASENAME@.cpp',
  arguments: ['@INPUT@', '-o', '@OUTPUT@']
  )

sources = g.process('bytecode-compiler/lox-bc.cpp2')

executable('lox-bc', sources,
   dependencies: [cpp2_dep])

