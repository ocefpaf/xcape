project(
    'xcape',
    ['c', 'fortran'],
    version: '1.0',
    meson_version: '>= 1.1.0',
    default_options: ['warning_level=1', 'buildtype=release']
)

py = import('python').find_installation(pure: false)
py_dep = py.dependency()

# NumPy include directory - needed in all submodules
incdir_numpy = run_command(py,
  [
    '-c',
    'import os; os.chdir(".."); import numpy; print(numpy.get_include())'
  ],
  check: true
).stdout().strip()

inc_np = include_directories(incdir_numpy)

incdir_f2py = incdir_numpy / '..' / '..' / 'f2py' / 'src'
inc_f2py = include_directories(incdir_f2py)
fortranobject_c = incdir_f2py / 'fortranobject.c'


CAPE_CODE_model_lev = custom_target(
    'CAPE_CODE_model_lev',
    input: ['xcape/fortran/CAPE_CODE_model_lev.pyf', 'xcape/fortran/CAPE_CODE_model_lev.f90'],
    output: ['CAPE_CODE_model_levmodule.c', 'CAPE_CODE_model_lev-f2pywrappers.f'],
    command : [py, '-m', 'numpy.f2py', '@INPUT@', '-m', 'CAPE_CODE_model_lev', '--lower'],
)

py.extension_module(
    'CAPE_CODE_model_lev',
    ['xcape/fortran/CAPE_CODE_model_lev.f90', CAPE_CODE_model_lev],
    fortranobject_c,
    include_directories: [inc_np, inc_f2py],
    dependencies: [py_dep],
    install : true,
    subdir: 'xcape/fortran',
)

CAPE_CODE_pressure_lev = custom_target(
    'CAPE_CODE_pressure_lev',
    input: ['xcape/fortran/CAPE_CODE_pressure_lev.pyf', 'xcape/fortran/CAPE_CODE_pressure_lev.f90'],
    output: ['CAPE_CODE_pressure_levmodule.c', 'CAPE_CODE_pressure_lev-f2pywrappers.f'],
    command : [py, '-m', 'numpy.f2py', '@INPUT@', '-m', 'CAPE_CODE_pressure_lev', '--lower'],
)

py.extension_module(
    'CAPE_CODE_pressure_lev',
    ['xcape/fortran/CAPE_CODE_pressure_lev.f90', CAPE_CODE_pressure_lev],
    fortranobject_c,
    include_directories: [inc_np, inc_f2py],
    dependencies: [py_dep],
    install : true,
    subdir: 'xcape/fortran',
)

Bunkers_model_lev = custom_target(
    'Bunkers_model_lev',
    input: ['xcape/fortran/Bunkers_model_lev.pyf', 'xcape/fortran/Bunkers_model_lev.f90'],
    output: ['Bunkers_model_levmodule.c', 'Bunkers_model_lev-f2pywrappers.f'],
    command : [py, '-m', 'numpy.f2py', '@INPUT@', '-m', 'Bunkers_model_lev', '--lower'],
)

py.extension_module(
    'Bunkers_model_lev',
    ['xcape/fortran/Bunkers_model_lev.f90', Bunkers_model_lev],
    fortranobject_c,
    include_directories: [inc_np, inc_f2py],
    dependencies: [py_dep],
    install : true,
    subdir: 'xcape/fortran',
)

Bunkers_pressure_lev = custom_target(
    'Bunkers_pressure_lev',
    input: ['xcape/fortran/Bunkers_pressure_lev.pyf', 'xcape/fortran/Bunkers_pressure_lev.f90'],
    output: ['Bunkers_pressure_levmodule.c', 'Bunkers_pressure_lev-f2pywrappers.f'],
    command : [py, '-m', 'numpy.f2py', '@INPUT@', '-m', 'Bunkers_pressure_lev', '--lower'],
)

py.extension_module(
    'Bunkers_pressure_lev',
    ['xcape/fortran/Bunkers_pressure_lev.f90', Bunkers_pressure_lev],
    fortranobject_c,
    include_directories: [inc_np, inc_f2py],
    dependencies: [py_dep],
    install : true,
    subdir: 'xcape/fortran',
)

SREH_model_lev = custom_target(
    'SREH_model_lev',
    input: ['xcape/fortran/SREH_model_lev.pyf', 'xcape/fortran/SREH_model_lev.f90'],
    output: ['SREH_model_levmodule.c', 'SREH_model_lev-f2pywrappers.f'],
    command : [py, '-m', 'numpy.f2py', '@INPUT@', '-m', 'SREH_model_lev', '--lower'],
)

py.extension_module(
    'SREH_model_lev',
    ['xcape/fortran/SREH_model_lev.f90', SREH_model_lev],
    fortranobject_c,
    include_directories: [inc_np, inc_f2py],
    dependencies: [py_dep],
    install : true,
    subdir: 'xcape/fortran',
)

SREH_pressure_lev = custom_target(
    'SREH_pressure_lev',
    input: ['xcape/fortran/SREH_pressure_lev.pyf', 'xcape/fortran/SREH_pressure_lev.f90'],
    output: ['SREH_pressure_levmodule.c', 'SREH_pressure_lev-f2pywrappers.f'],
    command : [py, '-m', 'numpy.f2py', '@INPUT@', '-m', 'SREH_pressure_lev', '--lower'],
)

py.extension_module(
    'SREH_pressure_lev',
    ['xcape/fortran/SREH_pressure_lev.f90', SREH_pressure_lev],
    fortranobject_c,
    include_directories: [inc_np, inc_f2py],
    dependencies: [py_dep],
    install : true,
    subdir: 'xcape/fortran',
)

stdheight_2D_model_lev = custom_target(
    'stdheight_2D_model_lev',
    input: ['xcape/fortran/stdheight_2D_model_lev.pyf', 'xcape/fortran/stdheight_2D_model_lev.f90'],
    output: ['stdheight_2D_model_levmodule.c', 'stdheight_2D_model_lev-f2pywrappers.f'],
    command : [py, '-m', 'numpy.f2py', '@INPUT@', '-m', 'stdheight_2D_model_lev', '--lower'],
)

py.extension_module(
    'stdheight_2D_model_lev',
    ['xcape/fortran/stdheight_2D_model_lev.f90', stdheight_2D_model_lev],
    fortranobject_c,
    include_directories: [inc_np, inc_f2py],
    dependencies: [py_dep],
    install : true,
    subdir: 'xcape/fortran',
)

stdheight_2D_pressure_lev = custom_target(
    'stdheight_2D_pressure_lev',
    input: ['xcape/fortran/stdheight_2D_pressure_lev.pyf', 'xcape/fortran/stdheight_2D_pressure_lev.f90'],
    output: ['stdheight_2D_pressure_levmodule.c', 'stdheight_2D_pressure_lev-f2pywrappers.f'],
    command : [py, '-m', 'numpy.f2py', '@INPUT@', '-m', 'stdheight_2D_pressure_lev', '--lower'],
)

py.extension_module(
    'stdheight_2D_pressure_lev',
    ['xcape/fortran/stdheight_2D_pressure_lev.f90', stdheight_2D_pressure_lev],
    fortranobject_c,
    include_directories: [inc_np, inc_f2py],
    dependencies: [py_dep],
    install : true,
    subdir: 'xcape/fortran',
)


py.install_sources(
    'xcape/__init__.py',
    'xcape/cape_fortran.py',
    'xcape/cape_numba.py',
    'xcape/core.py',
    'xcape/duck_array_ops.py',
    'xcape/srh.py',
    'xcape/stdheight.py',
    'xcape/xarray.py',
    subdir: 'xcape'
)
