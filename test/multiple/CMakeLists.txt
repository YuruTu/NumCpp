set(TARGET_NAME Multiple)

add_executable(${TARGET_NAME} 
    main.cpp
    function.cpp
)

set_target_properties(${TARGET_NAME}
    PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY ${OUTPUT_BINARY_DIR}
)

target_include_directories(${TARGET_NAME} PRIVATE 
    ./
    ${NUMCPP_INCLUDES}
)

target_link_libraries(${TARGET_NAME} PRIVATE 
    ${ALL_INTERFACE_TARGET}
)

add_test(NAME ${TARGET_NAME}
    COMMAND ${TARGET_NAME}
)
