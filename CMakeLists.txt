cmake_minimum_required(VERSION 3.28)

project(SystemC_Hello VERSION 1.0)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_executable(systemc-hello main.cpp
                Hello_SystemC.cpp Hello_SystemC.h)

include(FetchContent)

# SystemC
FetchContent_Declare(
  systemc
  URL https://github.com/accellera-official/systemc/archive/refs/tags/3.0.0_pub_rev_20231129.zip
)
FetchContent_MakeAvailable(systemc)
target_link_libraries(systemc-hello systemc)
