SET(test_name "pytest_random_linesegments" )

MESSAGE(STATUS "configuring py test: " ${test_name})


set( LINESEG_CASES 128 256 512 ) # 1024 2048 4096
foreach( CASE ${LINESEG_CASES} )
    ADD_TEST(${test_name}_${CASE} python ${CMAKE_SOURCE_DIR}/test/${test_name}/random_linesegments.py ${CASE})
    set_property(TEST ${test_name}_${CASE} PROPERTY ENVIRONMENT PYTHONPATH=${CMAKE_BINARY_DIR}:$ENV{PYTHONPATH})
endforeach()

