set(
	SSL_SRC
  ssl_stat.c
  t1_lib.c
  ktls.c
  tls_srp.c
  tls13_enc.c
  s3_msg.c
  ssl_cert.c
  ssl_err.c
  methods.c
  ssl_mcnf.c
  t1_trce.c
  d1_srtp.c
  s3_cbc.c
  ssl_conf.c
  s3_lib.c
  ssl_sess.c
  bio_ssl.c
  d1_msg.c
  ssl_ciph.c
  ssl_init.c
  ssl_lib.c
  ssl_rsa_legacy.c
  record/ssl3_record_tls13.c
  record/ssl3_buffer.c
  record/tls_pad.c
  record/ssl3_record.c
  record/dtls1_bitmap.c
  record/rec_layer_d1.c
  record/rec_layer_s3.c
  ssl_asn1.c
  statem/extensions_cust.c
  statem/statem_srvr.c
  statem/statem.c
  statem/extensions_srvr.c
  statem/statem_clnt.c
  statem/extensions.c
  statem/statem_dtls.c
  statem/extensions_clnt.c
  statem/statem_lib.c
  ssl_err_legacy.c
  d1_lib.c
  t1_enc.c
  s3_enc.c
  pqueue.c
  tls_depr.c
  ssl_txt.c
  ssl_utst.c
  ssl_rsa.c
)

add_library(ssl_obj OBJECT ${SSL_SRC})
target_include_directories(ssl_obj
	PRIVATE
		.
	PUBLIC
		../include)

add_library(ssl $<TARGET_OBJECTS:ssl_obj>)
target_include_directories(ssl
	PRIVATE
		.
	PUBLIC
		../include)

target_link_libraries(ssl crypto ${PLATFORM_LIBS})
