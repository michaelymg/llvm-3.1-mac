if( POLICY CMP0042 )
  set( CMAKE_MACOSX_RPATH ON )
endif()

add_llvm_loadable_module( BugpointPasses
  TestPasses.cpp
  )

add_dependencies(BugpointPasses bugpoint)
