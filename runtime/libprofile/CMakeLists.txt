set(SOURCES
  BasicBlockTracing.c
  CommonProfiling.c
  GCDAProfiling.c
  PathProfiling.c
  EdgeProfiling.c
  OptimalEdgeProfiling.c
  Profiling.h
  )

if( POLICY CMP0042 )
  set( CMAKE_MACOSX_RPATH ON )
endif()


add_llvm_library( profile_rt-static ${SOURCES} )
set_target_properties( profile_rt-static
  PROPERTIES
  OUTPUT_NAME "profile_rt" )

add_llvm_loadable_module( profile_rt-shared ${SOURCES} )
set_target_properties( profile_rt-shared
  PROPERTIES
  OUTPUT_NAME "profile_rt" )
