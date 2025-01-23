cmake_minimum_required(VERSION 3.28)
project(SqrtTest LANGUAGES C CXX)

## IDK WHAT ANY OF THIS MEANS ##
# set CPP standards
# set(CMAKE_CXX_STANDARD 13)
# set(CMAKE_CXX_STANDARD_REQUIRED ON)
# set(CMAKE_CXX_EXTENSIONS OFF) # force rely on the compiler only, and not on compiler extensions

## THIS IS NOT BEING USED RN ##
# add_subdirectory(src)
# add_subdirectory(tests) # you can nest subdirectories!!!!! then give them their own makefiles
 
# the generator must be specified the first time around , then it is saved in the cmake cache!

# Locate GTestc
find_package(GTest REQUIRED) # ???
include_directories(${GTEST_INCLUDE_DIRS}) # ???
 
# Link runTests with what we want to test and the GTest and pthread library
add_executable(executeTests sqrt_test.cpp) # make an executable called executeTests from the file sqrt_test.cpp
target_link_libraries(executeTests ${GTEST_LIBRARIES} pthread) # ???
# forms command to linker ^^ adding libraries like -L<> and -l<>