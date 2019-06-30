idf_component_register(SRCS "hello_world_main.c" INCLUDE_DIRS "lib/libwebsockets/include" "../build/esp-idf/main/lib/libwebsockets" REQUIRES nvs_flash mdns mbedtls lwip nghttp)

set(LWS_MBEDTLS_INCLUDE_DIRS ${IDF_PATH}/components/mbedtls/mbedtls/include;${IDF_PATH}/components/mbedtls/port/include)

set(LWS_WITH_ESP32 ON)

function(install)
endfunction()

function(export)
endfunction()

add_subdirectory(lib/libwebsockets)
idf_component_get_property(nvs_flash_lib nvs_flash COMPONENT_LIB)
idf_component_get_property(mdns_lib mdns COMPONENT_LIB)
set_property(TARGET websockets APPEND PROPERTY LINK_LIBRARIES ${nvs_flash_lib} ${mdns_lib})
set_property(TARGET websockets APPEND PROPERTY INTERFACE_LINK_LIBRARIES ${nvs_flash_lib} ${mdns_lib})
