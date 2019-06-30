idf_component_register(SRCS "hello_world_main.c" INCLUDE_DIRS "lib/libwebsockets/include" REQUIRES nvs_flash mdns mbedtls PRIV_REQUIRES lwip nghttp)

set(LWS_MBEDTLS_INCLUDE_DIRS ${IDF_PATH}/components/mbedtls/mbedtls/include;${IDF_PATH}/components/mbedtls/port/include)

set(LWS_WITH_ESP32 ON)

function(install)
endfunction()

function(export)
endfunction()

add_subdirectory(lib/libwebsockets)
target_link_libraries(${COMPONENT_LIB} PUBLIC libwebsockets)
