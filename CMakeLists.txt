cmake_minimum_required(VERSION 3.18 FATAL_ERROR)
project(lltm_xpu)

find_package(Python COMPONENTS Interpreter Development)
find_package(Torch REQUIRED)
find_package(IntelExtensionPytorch REQUIRED)

#The SYCL kernel should be compiled with "-fsycl"
set_source_files_properties(lltm_xpu_kernel.cpp PROPERTIES COMPILE_FLAGS "-fsycl")

add_library(lltm_xpu SHARED lltm_xpu.cpp lltm_xpu_kernel.cpp)
target_link_libraries(lltm_xpu "${TORCH_LIBRARIES}")
target_link_libraries(lltm_xpu "${TORCH_IPEX_LIBRARIES}")
target_include_directories(lltm_xpu PUBLIC "${Python_INCLUDE_DIRS}")
target_include_directories(lltm_xpu PUBLIC "${TORCH_IPEX_INCLUDE_DIRS}")

set_property(TARGET lltm_xpu PROPERTY CXX_STANDARD 14)