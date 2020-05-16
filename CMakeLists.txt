idf_component_register(
        INCLUDE_DIRS "libwebsockets/include" "${IDF_PATH}/components/lws-esp32/libwebsockets"
        REQUIRES nvs_flash mdns mbedtls lwip nghttp bootloader_support
        )

cmake_policy(SET CMP0077 NEW)

set(LWS_MBEDTLS_INCLUDE_DIRS ${IDF_PATH}/components/mbedtls/mbedtls/include;${IDF_PATH}/components/mbedtls/port/include)

set(LWS_WITH_ESP32 ON)

function(install)
endfunction()

function(export)
endfunction()

add_subdirectory(libwebsockets)
idf_component_get_property(nvs_flash_lib nvs_flash COMPONENT_LIB)
idf_component_get_property(mdns_lib mdns COMPONENT_LIB)
idf_component_get_property(bootloader_support_lib bootloader_support COMPONENT_LIB)
idf_component_get_property(app_update_lib app_update COMPONENT_LIB)
set_property(TARGET websockets APPEND PROPERTY LINK_LIBRARIES
        ${nvs_flash_lib}
        ${mdns_lib}
        ${bootloader_support_lib}
        ${app_update_lib})
set_property(TARGET websockets APPEND PROPERTY INTERFACE_LINK_LIBRARIES
        ${nvs_flash_lib}
        ${mdns_lib}
        ${bootloader_support_lib}
        ${app_update_lib})
