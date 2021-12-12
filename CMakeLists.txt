cmake_minimum_required(VERSION 3.11)

project (OpenSSL VERSION 3.1)

set(OPENSSL_INCLUDE_DIR ${PROJECT_SOURCE_DIR}/include)
set(OPENSSL_LIBRARIES crypto ssl tls)
set(OPENSSL_CRYPTO_LIBRARY crypto)
set(OPENSSL_SSL_LIBRARY ssl)
set(OPENSSL_TLS_LIBRARY)

add_subdirectory(crypto)
add_subdirectory(ssl)
add_subdirectory(tls)

set(OPENSSL_FOUND 1)
