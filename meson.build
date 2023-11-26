project('cpp2lox',
 'cpp',
 default_options : ['cpp_std=c++20'])

# cppfront support 
cpp2_dep = dependency('cpp2')
cppfront = find_program('cppfront')
g = generator(cppfront,
  output: '@BASENAME@.cpp',
  arguments: ['@INPUT@', '-o', '@OUTPUT@']
  )

# TODO: Tree Walk Intrepreter

# Byte-code compiler
bc_inc = include_directories('bytecode-compiler')
bc_sources = g.process('bytecode-compiler/lox-bc.cpp2',
                      include_directories: bc_inc)
executable('lox-bc', bc_sources,
   dependencies: [cpp2_dep])

