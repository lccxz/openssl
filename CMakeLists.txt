cmake_minimum_required(VERSION 3.11)

project(OpenSSL VERSION 1.1)

get_filename_component(LIBDIR ${PROJECT_SOURCE_DIR} DIRECTORY)

if (NOT EXISTS "${LIBDIR}/install/openssl/lib/libssl.a")
    execute_process(
        WORKING_DIRECTORY "${PROJECT_SOURCE_DIR}"
        COMMAND "./config"
            "--prefix=${LIBDIR}/install/openssl"
            "--openssldir=${LIBDIR}/install/ssl"
        RESULT_VARIABLE ret
    )
    if(${ret})
        message(FATAL_ERROR "OpenSSL configure error")
    endif()

    execute_process(
        WORKING_DIRECTORY "${PROJECT_SOURCE_DIR}"
        COMMAND "make"
        RESULT_VARIABLE ret
    )
    if(${ret})
        message(FATAL_ERROR "OpenSSL make error")
    endif()

    execute_process(
            WORKING_DIRECTORY "${PROJECT_SOURCE_DIR}"
            COMMAND "make" "install"
            RESULT_VARIABLE ret
    )
    if(${ret})
        message(FATAL_ERROR "OpenSSL install error")
    endif()
endif()

set(OPENSSL_ROOT_DIR "${LIBDIR}/install/openssl")
find_package(OpenSSL REQUIRED)
