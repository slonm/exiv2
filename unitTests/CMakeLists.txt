add_executable(unit_tests mainTestRunner.cpp
    test_types.cpp
)

#TODO Use GTest::GTest once we upgrade the minimum CMake version required
target_link_libraries(unit_tests 
    PRIVATE
        exiv2lib
        ${GTEST_BOTH_LIBRARIES}
)

target_include_directories(unit_tests
    PRIVATE
        ${GTEST_INCLUDE_DIRS}
)

target_compile_definitions(unit_tests
    PRIVATE
        GTEST_LINKED_AS_SHARED_LIBRARY=1
)
