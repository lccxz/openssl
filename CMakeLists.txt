cmake_minimum_required(VERSION 3.11)

project(OpenSSL VERSION 3.1)

if (NOT EXISTS "${PROJECT_SOURCE_DIR}/libssl.a")
    execute_process(
        WORKING_DIRECTORY "${PROJECT_SOURCE_DIR}"
        COMMAND "perl" "Configure"
        RESULT_VARIABLE ret
    )
    if(ret NOT EQUAL "0")
        message(FATAL_ERROR "OpenSSL configure error")
    endif()

    execute_process(
        WORKING_DIRECTORY "${PROJECT_SOURCE_DIR}"
        COMMAND "make"
        RESULT_VARIABLE ret
    )
    if(ret NOT EQUAL "0")
        message(FATAL_ERROR "OpenSSL make error")
    endif()
endif()

set(OPENSSL_INCLUDE_DIR ${PROJECT_SOURCE_DIR}/include PARENT_SCOPE)
set(OPENSSL_LIBRARIES libcrypto libssl PARENT_SCOPE)
set(OPENSSL_CRYPTO_LIBRARY "${PROJECT_SOURCE_DIR}/libcrypto.a" PARENT_SCOPE)
set(OPENSSL_SSL_LIBRARY "${PROJECT_SOURCE_DIR}/libssl.a" PARENT_SCOPE)
set(OPENSSL_ROOT_DIR "${PROJECT_SOURCE_DIR}" PARENT_SCOPE)

find_library(OpenSSL NAMES OpenSSL libcrypto libssl HINTS "${PROJECT_SOURCE_DIR}")
