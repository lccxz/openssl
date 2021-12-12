if(HOST_ASM_ELF_ARMV4)
	set(
		ASM_ARMV4_ELF_SRC
		aes/aes-elf-armv4.S
		bn/gf2m-elf-armv4.S
		bn/mont-elf-armv4.S
		sha/sha1-elf-armv4.S
		sha/sha512-elf-armv4.S
		sha/sha256-elf-armv4.S
		modes/ghash-elf-armv4.S
		armv4cpuid.S
		armcap.c
	)
	add_definitions(-DAES_ASM)
	add_definitions(-DOPENSSL_BN_ASM_MONT)
	add_definitions(-DOPENSSL_BN_ASM_GF2m)
	add_definitions(-DGHASH_ASM)
	add_definitions(-DSHA1_ASM)
	add_definitions(-DSHA256_ASM)
	add_definitions(-DSHA512_ASM)
	add_definitions(-DOPENSSL_CPUID_OBJ)
	set_property(SOURCE ${ASM_ARMV4_ELF_SRC} PROPERTY LANGUAGE C)
	set(CRYPTO_SRC ${CRYPTO_SRC} ${ASM_ARMV4_ELF_SRC})
endif()

if(HOST_ASM_ELF_X86_64)
	set(
		ASM_X86_64_ELF_SRC
		aes/aes-elf-x86_64.S
		aes/bsaes-elf-x86_64.S
		aes/vpaes-elf-x86_64.S
		aes/aesni-elf-x86_64.S
		aes/aesni-sha1-elf-x86_64.S
		bn/modexp512-elf-x86_64.S
		bn/mont-elf-x86_64.S
		bn/mont5-elf-x86_64.S
		bn/gf2m-elf-x86_64.S
		camellia/cmll-elf-x86_64.S
		md5/md5-elf-x86_64.S
		modes/ghash-elf-x86_64.S
		rc4/rc4-elf-x86_64.S
		rc4/rc4-md5-elf-x86_64.S
		sha/sha1-elf-x86_64.S
		sha/sha256-elf-x86_64.S
		sha/sha512-elf-x86_64.S
		whrlpool/wp-elf-x86_64.S
		cpuid-elf-x86_64.S
	)
	add_definitions(-DAES_ASM)
	add_definitions(-DBSAES_ASM)
	add_definitions(-DVPAES_ASM)
	add_definitions(-DOPENSSL_IA32_SSE2)
	add_definitions(-DOPENSSL_BN_ASM_MONT)
	add_definitions(-DOPENSSL_BN_ASM_MONT5)
	add_definitions(-DOPENSSL_BN_ASM_GF2m)
	add_definitions(-DMD5_ASM)
	add_definitions(-DGHASH_ASM)
	add_definitions(-DRSA_ASM)
	add_definitions(-DSHA1_ASM)
	add_definitions(-DSHA256_ASM)
	add_definitions(-DSHA512_ASM)
	add_definitions(-DWHIRLPOOL_ASM)
	add_definitions(-DOPENSSL_CPUID_OBJ)
	set(CRYPTO_SRC ${CRYPTO_SRC} ${ASM_X86_64_ELF_SRC})
	set_property(SOURCE ${ASM_X86_64_ELF_SRC} PROPERTY LANGUAGE C)
endif()

if(HOST_ASM_MACOSX_X86_64)
	set(
		ASM_X86_64_MACOSX_SRC
		aes/aes-macosx-x86_64.S
		aes/bsaes-macosx-x86_64.S
		aes/vpaes-macosx-x86_64.S
		aes/aesni-macosx-x86_64.S
		aes/aesni-sha1-macosx-x86_64.S
		bn/modexp512-macosx-x86_64.S
		bn/mont-macosx-x86_64.S
		bn/mont5-macosx-x86_64.S
		bn/gf2m-macosx-x86_64.S
		camellia/cmll-macosx-x86_64.S
		md5/md5-macosx-x86_64.S
		modes/ghash-macosx-x86_64.S
		rc4/rc4-macosx-x86_64.S
		rc4/rc4-md5-macosx-x86_64.S
		sha/sha1-macosx-x86_64.S
		sha/sha256-macosx-x86_64.S
		sha/sha512-macosx-x86_64.S
		whrlpool/wp-macosx-x86_64.S
		cpuid-macosx-x86_64.S
	)
	add_definitions(-DAES_ASM)
	add_definitions(-DBSAES_ASM)
	add_definitions(-DVPAES_ASM)
	add_definitions(-DOPENSSL_IA32_SSE2)
	add_definitions(-DOPENSSL_BN_ASM_MONT)
	add_definitions(-DOPENSSL_BN_ASM_MONT5)
	add_definitions(-DOPENSSL_BN_ASM_GF2m)
	add_definitions(-DMD5_ASM)
	add_definitions(-DGHASH_ASM)
	add_definitions(-DRSA_ASM)
	add_definitions(-DSHA1_ASM)
	add_definitions(-DSHA256_ASM)
	add_definitions(-DSHA512_ASM)
	add_definitions(-DWHIRLPOOL_ASM)
	add_definitions(-DOPENSSL_CPUID_OBJ)
	set(CRYPTO_SRC ${CRYPTO_SRC} ${ASM_X86_64_MACOSX_SRC})
	set_property(SOURCE ${ASM_X86_64_MACOSX_SRC} PROPERTY LANGUAGE C)
	set_property(SOURCE ${ASM_X86_64_MACOSX_SRC} PROPERTY XCODE_EXPLICIT_FILE_TYPE "sourcecode.asm")
endif()

if(HOST_ASM_MASM_X86_64)
	set(
		ASM_X86_64_MASM_SRC
		aes/aes-masm-x86_64.S
		aes/bsaes-masm-x86_64.S
		aes/vpaes-masm-x86_64.S
		aes/aesni-masm-x86_64.S
		aes/aesni-sha1-masm-x86_64.S
		#bn/modexp512-masm-x86_64.S
		#bn/mont-masm-x86_64.S
		#bn/mont5-masm-x86_64.S
		#bn/gf2m-masm-x86_64.S
		camellia/cmll-masm-x86_64.S
		md5/md5-masm-x86_64.S
		modes/ghash-masm-x86_64.S
		rc4/rc4-masm-x86_64.S
		rc4/rc4-md5-masm-x86_64.S
		sha/sha1-masm-x86_64.S
		sha/sha256-masm-x86_64.S
		sha/sha512-masm-x86_64.S
		whrlpool/wp-masm-x86_64.S
		cpuid-masm-x86_64.S
	)
	add_definitions(-DAES_ASM)
	add_definitions(-DBSAES_ASM)
	add_definitions(-DVPAES_ASM)
	add_definitions(-DOPENSSL_IA32_SSE2)
	#add_definitions(-DOPENSSL_BN_ASM_MONT)
	#add_definitions(-DOPENSSL_BN_ASM_MONT5)
	#add_definitions(-DOPENSSL_BN_ASM_GF2m)
	add_definitions(-DMD5_ASM)
	add_definitions(-DGHASH_ASM)
	add_definitions(-DRSA_ASM)
	add_definitions(-DSHA1_ASM)
	add_definitions(-DSHA256_ASM)
	add_definitions(-DSHA512_ASM)
	add_definitions(-DWHIRLPOOL_ASM)
	add_definitions(-DOPENSSL_CPUID_OBJ)
	set(CRYPTO_SRC ${CRYPTO_SRC} ${ASM_X86_64_MASM_SRC})
	set_property(SOURCE ${ASM_X86_64_MASM_SRC} PROPERTY LANGUAGE ASM_MASM)
endif()

if(HOST_ASM_MINGW64_X86_64)
	set(
		ASM_X86_64_MINGW64_SRC
		aes/aes-mingw64-x86_64.S
		aes/bsaes-mingw64-x86_64.S
		aes/vpaes-mingw64-x86_64.S
		aes/aesni-mingw64-x86_64.S
		aes/aesni-sha1-mingw64-x86_64.S
		#bn/modexp512-mingw64-x86_64.S
		#bn/mont-mingw64-x86_64.S
		#bn/mont5-mingw64-x86_64.S
		#bn/gf2m-mingw64-x86_64.S
		camellia/cmll-mingw64-x86_64.S
		md5/md5-mingw64-x86_64.S
		modes/ghash-mingw64-x86_64.S
		rc4/rc4-mingw64-x86_64.S
		rc4/rc4-md5-mingw64-x86_64.S
		sha/sha1-mingw64-x86_64.S
		sha/sha256-mingw64-x86_64.S
		sha/sha512-mingw64-x86_64.S
		whrlpool/wp-mingw64-x86_64.S
		cpuid-mingw64-x86_64.S
	)
	add_definitions(-DAES_ASM)
	add_definitions(-DBSAES_ASM)
	add_definitions(-DVPAES_ASM)
	add_definitions(-DOPENSSL_IA32_SSE2)
	#add_definitions(-DOPENSSL_BN_ASM_MONT)
	#add_definitions(-DOPENSSL_BN_ASM_MONT5)
	#add_definitions(-DOPENSSL_BN_ASM_GF2m)
	add_definitions(-DMD5_ASM)
	add_definitions(-DGHASH_ASM)
	add_definitions(-DRSA_ASM)
	add_definitions(-DSHA1_ASM)
	add_definitions(-DSHA256_ASM)
	add_definitions(-DSHA512_ASM)
	add_definitions(-DWHIRLPOOL_ASM)
	add_definitions(-DOPENSSL_CPUID_OBJ)
	set(CRYPTO_SRC ${CRYPTO_SRC} ${ASM_X86_64_MINGW64_SRC})
	set_property(SOURCE ${ASM_X86_64_MINGW64_SRC} PROPERTY LANGUAGE C)
endif()

if((NOT HOST_ASM_ELF_X86_64) AND
	(NOT HOST_ASM_MACOSX_X86_64) AND
	(NOT HOST_ASM_MASM_X86_64) AND
	(NOT HOST_ASM_MINGW64_X86_64) AND
	(NOT HOST_ASM_ELF_ARMV4))
	set(
		CRYPTO_SRC
		${CRYPTO_SRC}
		aes/aes_core.c
	)
endif()

if((NOT HOST_ASM_ELF_X86_64) AND
	(NOT HOST_ASM_MACOSX_X86_64) AND
	(NOT HOST_ASM_MASM_X86_64) AND
	(NOT HOST_ASM_MINGW64_X86_64))
	set(
		CRYPTO_SRC
		${CRYPTO_SRC}
		aes/aes_cbc.c
		camellia/camellia.c
		camellia/cmll_cbc.c
		rc4/rc4_enc.c
		rc4/rc4_skey.c
		whrlpool/wp_block.c
	)
endif()

set(
	CRYPTO_SRC
	${CRYPTO_SRC}
  seed/seed_cfb.c
  seed/seed_ofb.c
  seed/seed_cbc.c
  seed/seed_ecb.c
  seed/seed.c
  cpuid.c
  o_fopen.c
  sparcv9cap.c
  cast/c_ecb.c
  cast/c_enc.c
  cast/c_ofb64.c
  cast/c_skey.c
  cast/c_cfb64.c
  store/store_lib.c
  store/store_err.c
  store/store_strings.c
  store/store_register.c
  store/store_init.c
  store/store_meth.c
  store/store_result.c
  buffer/buffer.c
  buffer/buf_err.c
  ocsp/v3_ocsp.c
  ocsp/ocsp_vfy.c
  ocsp/ocsp_http.c
  ocsp/ocsp_srv.c
  ocsp/ocsp_err.c
  ocsp/ocsp_ext.c
  ocsp/ocsp_cl.c
  ocsp/ocsp_asn.c
  ocsp/ocsp_lib.c
  ocsp/ocsp_prn.c
  params_dup.c
  o_time.c
  packet.c
  o_dir.c
  bn/bn_div.c
  bn/bn_gcd.c
  bn/bn_asm.c
  bn/bn_prime.c
  bn/bn_x931p.c
  bn/bn_add.c
  bn/bn_exp2.c
  bn/bn_sparc.c
  bn/bn_nist.c
  bn/bn_sqr.c
  bn/bn_err.c
  bn/bn_mod.c
  bn/bn_lib.c
  bn/bn_sqrt.c
  bn/asm/x86_64-gcc.c
  bn/bn_ctx.c
  bn/bn_word.c
  bn/bn_blind.c
  bn/bn_ppc.c
  bn/bn_mont.c
  bn/bn_gf2m.c
  bn/bn_const.c
  bn/rsaz_exp_x2.c
  bn/bn_dh.c
  bn/bn_rsa_fips186_4.c
  bn/bn_mpi.c
  bn/bn_intern.c
  bn/bn_conv.c
  bn/bn_recp.c
  bn/bn_shift.c
  bn/bn_print.c
  bn/bn_exp.c
  bn/bn_mul.c
  bn/bn_rand.c
  bn/rsaz_exp.c
  bn/bn_depr.c
  bn/bn_srp.c
  bn/bn_kron.c
  LPdir_win32.c
  punycode.c
  txt_db/txt_db.c
  whrlpool/wp_block.c
  whrlpool/wp_dgst.c
  rand/rand_err.c
  rand/rand_meth.c
  rand/prov_seed.c
  rand/rand_egd.c
  rand/rand_pool.c
  rand/rand_lib.c
  rand/randfile.c
  rand/rand_deprecated.c
  threads_lib.c
  provider_core.c
  LPdir_nyi.c
  sm3/legacy_sm3.c
  sm3/sm3.c
  dllmain.c
  threads_none.c
  provider_child.c
  threads_pthread.c
  async/async.c
  async/async_err.c
  async/arch/async_posix.c
  async/arch/async_null.c
  async/arch/async_win.c
  async/async_wait.c
  ts/ts_lib.c
  ts/ts_err.c
  ts/ts_rsp_utils.c
  ts/ts_rsp_sign.c
  ts/ts_asn1.c
  ts/ts_rsp_verify.c
  ts/ts_req_utils.c
  ts/ts_conf.c
  ts/ts_verify_ctx.c
  ts/ts_req_print.c
  ts/ts_rsp_print.c
  param_build.c
  asn1/bio_asn1.c
  asn1/a_mbstr.c
  asn1/f_string.c
  asn1/a_int.c
  asn1/x_val.c
  asn1/tasn_typ.c
  asn1/t_pkey.c
  asn1/i2d_evp.c
  asn1/a_print.c
  asn1/t_spki.c
  asn1/asn_pack.c
  asn1/ameth_lib.c
  asn1/tasn_enc.c
  asn1/a_utf8.c
  asn1/p8_pkey.c
  asn1/evp_asn1.c
  asn1/p5_pbev2.c
  asn1/a_object.c
  asn1/x_spki.c
  asn1/tasn_prn.c
  asn1/p5_pbe.c
  asn1/asn_mstbl.c
  asn1/asn1_item_list.c
  asn1/a_strnid.c
  asn1/tasn_new.c
  asn1/x_int64.c
  asn1/a_strex.c
  asn1/tasn_dec.c
  asn1/a_d2i_fp.c
  asn1/d2i_param.c
  asn1/f_int.c
  asn1/asn1_gen.c
  asn1/x_info.c
  asn1/n_pkey.c
  asn1/asn1_parse.c
  asn1/a_bitstr.c
  asn1/d2i_pr.c
  asn1/a_octet.c
  asn1/nsseq.c
  asn1/a_time.c
  asn1/a_type.c
  asn1/x_sig.c
  asn1/x_pkey.c
  asn1/a_utctm.c
  asn1/a_dup.c
  asn1/x_bignum.c
  asn1/tasn_utl.c
  asn1/a_gentm.c
  asn1/a_sign.c
  asn1/d2i_pu.c
  asn1/x_long.c
  asn1/a_i2d_fp.c
  asn1/bio_ndef.c
  asn1/x_algor.c
  asn1/asn_mime.c
  asn1/p5_scrypt.c
  asn1/tasn_fre.c
  asn1/asn1_lib.c
  asn1/a_verify.c
  asn1/tasn_scn.c
  asn1/a_digest.c
  asn1/asn_moid.c
  asn1/t_bitst.c
  asn1/asn1_err.c
  mem_sec.c
  stack/stack.c
  camellia/camellia.c
  camellia/cmll_ctr.c
  camellia/cmll_ecb.c
  camellia/cmll_ofb.c
  camellia/cmll_cbc.c
  camellia/cmll_misc.c
  camellia/cmll_cfb.c
  threads_win.c
  trace.c
  ess/ess_lib.c
  ess/ess_asn1.c
  ess/ess_err.c
  ctype.c
  uid.c
  conf/conf_ssl.c
  conf/conf_def.c
  conf/conf_sap.c
  conf/conf_mod.c
  conf/conf_mall.c
  conf/conf_lib.c
  conf/conf_api.c
  conf/conf_err.c
  ec/curve448/curve448.c
  ec/curve448/curve448_tables.c
  ec/curve448/scalar.c
  ec/curve448/f_generic.c
  ec/curve448/eddsa.c
  ec/curve448/arch_32/f_impl32.c
  ec/curve448/arch_64/f_impl64.c
  ec/ecx_meth.c
  ec/ec_pmeth.c
  ec/ec_mult.c
  ec/ecp_smpl.c
  ec/ecdsa_ossl.c
  ec/ec_curve.c
  ec/ecp_nistputil.c
  ec/ec_key.c
  ec/ecp_nistp521.c
  ec/ecp_nistp256.c
  ec/ec_cvt.c
  ec/ecdsa_sign.c
  ec/curve25519.c
  ec/ec_print.c
  ec/ecx_s390x.c
  ec/ec_kmeth.c
  ec/ecdh_ossl.c
  ec/ec_ameth.c
  ec/ecx_backend.c
  ec/eck_prn.c
  ec/ec_check.c
  ec/ecp_nistp224.c
  ec/ec_deprecated.c
  ec/ecp_nist.c
  ec/ec_asn1.c
  ec/ec_backend.c
  ec/ecp_nistz256.c
  ec/ecp_nistz256_table.c
  ec/ecp_ppc.c
  ec/ecdsa_vrf.c
  ec/ec2_oct.c
  ec/ec_lib.c
  ec/ecx_key.c
  ec/ec_oct.c
  ec/ecp_s390x_nistp.c
  ec/ecdh_kdf.c
  ec/ec2_smpl.c
  ec/ec_err.c
  ec/ecp_mont.c
  ec/ecp_oct.c
  md5/md5_one.c
  md5/md5_sha1.c
  md5/md5_dgst.c
  dh/dh_kdf.c
  dh/dh_ameth.c
  dh/dh_asn1.c
  dh/dh_depr.c
  dh/dh_backend.c
  dh/dh_rfc5114.c
  dh/dh_prn.c
  dh/dh_key.c
  dh/dh_pmeth.c
  dh/dh_err.c
  dh/dh_lib.c
  dh/dh_meth.c
  dh/dh_gen.c
  dh/dh_group_params.c
  dh/dh_check.c
  ppccap.c
  provider_predefined.c
  o_str.c
  ebcdic.c
  srp/srp_vfy.c
  srp/srp_lib.c
  rc2/rc2cfb64.c
  rc2/rc2_skey.c
  rc2/rc2_cbc.c
  rc2/rc2_ecb.c
  rc2/rc2ofb64.c
  dsa/dsa_key.c
  dsa/dsa_pmeth.c
  dsa/dsa_gen.c
  dsa/dsa_prn.c
  dsa/dsa_meth.c
  dsa/dsa_backend.c
  dsa/dsa_sign.c
  dsa/dsa_lib.c
  dsa/dsa_err.c
  dsa/dsa_check.c
  dsa/dsa_depr.c
  dsa/dsa_ossl.c
  dsa/dsa_vrf.c
  dsa/dsa_asn1.c
  dsa/dsa_ameth.c
  LPdir_vms.c
  cmp/cmp_server.c
  cmp/cmp_protect.c
  cmp/cmp_http.c
  cmp/cmp_err.c
  cmp/cmp_ctx.c
  cmp/cmp_status.c
  cmp/cmp_asn.c
  cmp/cmp_client.c
  cmp/cmp_hdr.c
  cmp/cmp_vfy.c
  cmp/cmp_msg.c
  cmp/cmp_util.c
  err/err_blocks.c
  err/err_all.c
  err/err.c
  err/err_prn.c
  err/err_all_legacy.c
  param_build_set.c
  property/defn_cache.c
  property/property_err.c
  property/property_parse.c
  property/property_query.c
  property/property_string.c
  property/property.c
  initthread.c
  siphash/siphash.c
  bf/bf_ecb.c
  bf/bf_skey.c
  bf/bf_cfb64.c
  bf/bf_enc.c
  bf/bf_ofb64.c
  getenv.c
  mem_clr.c
  des/ofb_enc.c
  des/xcbc_enc.c
  des/ecb3_enc.c
  des/ncbc_enc.c
  des/cfb64enc.c
  des/fcrypt_b.c
  des/cbc_cksm.c
  des/rand_key.c
  des/qud_cksm.c
  des/cfb64ede.c
  des/ofb64ede.c
  des/fcrypt.c
  des/ecb_enc.c
  des/str2key.c
  des/des_enc.c
  des/cbc_enc.c
  des/set_key.c
  des/pcbc_enc.c
  des/cfb_enc.c
  des/ofb64enc.c
  sm4/sm4.c
  aria/aria.c
  rsa/rsa_oaep.c
  rsa/rsa_sp800_56b_check.c
  rsa/rsa_prn.c
  rsa/rsa_ossl.c
  rsa/rsa_schemes.c
  rsa/rsa_mp.c
  rsa/rsa_x931.c
  rsa/rsa_chk.c
  rsa/rsa_acvp_test_params.c
  rsa/rsa_mp_names.c
  rsa/rsa_err.c
  rsa/rsa_depr.c
  rsa/rsa_x931g.c
  rsa/rsa_pmeth.c
  rsa/rsa_sign.c
  rsa/rsa_asn1.c
  rsa/rsa_lib.c
  rsa/rsa_meth.c
  rsa/rsa_ameth.c
  rsa/rsa_pk1.c
  rsa/rsa_saos.c
  rsa/rsa_pss.c
  rsa/rsa_sp800_56b_gen.c
  rsa/rsa_none.c
  rsa/rsa_crpt.c
  rsa/rsa_backend.c
  rsa/rsa_gen.c
  core_fetch.c
  pkcs7/pk7_smime.c
  pkcs7/pk7_attr.c
  pkcs7/pk7_doit.c
  pkcs7/pk7_asn1.c
  pkcs7/pkcs7err.c
  pkcs7/pk7_mime.c
  pkcs7/pk7_lib.c
  pkcs7/bio_pk7.c
  armcap.c
  cversion.c
  cryptlib.c
  dso/dso_openssl.c
  dso/dso_err.c
  dso/dso_lib.c
  dso/dso_win32.c
  dso/dso_dl.c
  dso/dso_vms.c
  dso/dso_dlfcn.c
  LPdir_wince.c
  bsearch.c
  cms/cms_rsa.c
  cms/cms_cd.c
  cms/cms_lib.c
  cms/cms_asn1.c
  cms/cms_smime.c
  cms/cms_kari.c
  cms/cms_pwri.c
  cms/cms_att.c
  cms/cms_dh.c
  cms/cms_sd.c
  cms/cms_ec.c
  cms/cms_dd.c
  cms/cms_enc.c
  cms/cms_ess.c
  cms/cms_env.c
  cms/cms_io.c
  cms/cms_err.c
  LPdir_win.c
  md2/md2_dgst.c
  md2/md2_one.c
  o_init.c
  modes/ofb128.c
  modes/cts128.c
  modes/ctr128.c
  modes/ccm128.c
  modes/wrap128.c
  modes/cfb128.c
  modes/ocb128.c
  modes/siv128.c
  modes/gcm128.c
  modes/cbc128.c
  modes/xts128.c
  provider.c
  lhash/lhash.c
  lhash/lh_stats.c
  passphrase.c
  idea/i_cfb64.c
  idea/i_ecb.c
  idea/i_skey.c
  idea/i_ofb64.c
  idea/i_cbc.c
  comp/comp_lib.c
  comp/c_zlib.c
  comp/comp_err.c
  sparse_array.c
  provider_conf.c
  rc4/rc4_skey.c
  rc4/rc4_enc.c
  http/http_client.c
  http/http_err.c
  http/http_lib.c
  md4/md4_one.c
  md4/md4_dgst.c
  evp/e_camellia.c
  evp/legacy_mdc2.c
  evp/pbe_scrypt.c
  evp/e_old.c
  evp/digest.c
  evp/evp_utils.c
  evp/ec_ctrl.c
  evp/p5_crpt2.c
  evp/evp_key.c
  evp/e_xcbc_d.c
  evp/legacy_md5.c
  evp/p_sign.c
  evp/legacy_md4.c
  evp/p_lib.c
  evp/evp_cnf.c
  evp/e_rc4_hmac_md5.c
  evp/e_aes.c
  evp/p_open.c
  evp/legacy_md5_sha1.c
  evp/exchange.c
  evp/kdf_meth.c
  evp/legacy_sha.c
  evp/legacy_blake2.c
  evp/p_verify.c
  evp/evp_fetch.c
  evp/p_legacy.c
  evp/c_alld.c
  evp/e_aria.c
  evp/e_bf.c
  evp/evp_pkey.c
  evp/e_null.c
  evp/evp_pbe.c
  evp/m_null.c
  evp/e_aes_cbc_hmac_sha256.c
  evp/e_cast.c
  evp/pmeth_check.c
  evp/signature.c
  evp/keymgmt_meth.c
  evp/bio_b64.c
  evp/evp_lib.c
  evp/bio_ok.c
  evp/names.c
  evp/pmeth_lib.c
  evp/e_rc5.c
  evp/bio_md.c
  evp/pmeth_gn.c
  evp/keymgmt_lib.c
  evp/c_allc.c
  evp/m_sigver.c
  evp/e_seed.c
  evp/mac_meth.c
  evp/e_rc4.c
  evp/evp_enc.c
  evp/kem.c
  evp/ctrl_params_translate.c
  evp/asymcipher.c
  evp/p_enc.c
  evp/p_seal.c
  evp/legacy_ripemd.c
  evp/e_des.c
  evp/cmeth_lib.c
  evp/kdf_lib.c
  evp/mac_lib.c
  evp/e_idea.c
  evp/bio_enc.c
  evp/e_chacha20_poly1305.c
  evp/dsa_ctrl.c
  evp/ec_support.c
  evp/p_dec.c
  evp/e_sm4.c
  evp/legacy_wp.c
  evp/e_rc2.c
  evp/e_des3.c
  evp/p5_crpt.c
  evp/evp_err.c
  evp/dh_ctrl.c
  evp/evp_rand.c
  evp/encode.c
  evp/dh_support.c
  evp/legacy_md2.c
  evp/e_aes_cbc_hmac_sha1.c
  pem/pem_pk8.c
  pem/pem_lib.c
  pem/pem_sign.c
  pem/pvkfmt.c
  pem/pem_x509.c
  pem/pem_oth.c
  pem/pem_pkey.c
  pem/pem_all.c
  pem/pem_info.c
  pem/pem_xaux.c
  pem/pem_err.c
  kdf/kdf_err.c
  ffc/ffc_params.c
  ffc/ffc_dh.c
  ffc/ffc_key_validate.c
  ffc/ffc_params_generate.c
  ffc/ffc_params_validate.c
  ffc/ffc_backend.c
  ffc/ffc_key_generate.c
  params.c
  ex_data.c
  hmac/hmac.c
  ui/ui_null.c
  ui/ui_openssl.c
  ui/ui_util.c
  ui/ui_lib.c
  ui/ui_err.c
  cpt_err.c
  aes/aes_cfb.c
  aes/aes_ecb.c
  aes/aes_core.c
  aes/aes_ofb.c
  aes/aes_cbc.c
  aes/aes_ige.c
  aes/aes_x86core.c
  aes/aes_wrap.c
  aes/aes_misc.c
  init.c
  encode_decode/encoder_pkey.c
  encode_decode/decoder_err.c
  encode_decode/decoder_lib.c
  encode_decode/encoder_err.c
  encode_decode/encoder_lib.c
  encode_decode/decoder_pkey.c
  encode_decode/encoder_meth.c
  encode_decode/decoder_meth.c
  core_algorithm.c
  objects/obj_lib.c
  objects/o_names.c
  objects/obj_dat.c
  objects/obj_xref.c
  objects/obj_err.c
  bio/bio_err.c
  bio/bf_prefix.c
  bio/bss_log.c
  bio/bss_acpt.c
  bio/bf_readbuff.c
  bio/bss_file.c
  bio/bss_dgram.c
  bio/bio_dump.c
  bio/bf_null.c
  bio/bss_null.c
  bio/bio_sock.c
  bio/bss_core.c
  bio/bio_meth.c
  bio/bss_bio.c
  bio/bss_conn.c
  bio/bio_cb.c
  bio/bss_mem.c
  bio/bf_buff.c
  bio/bss_sock.c
  bio/ossl_core_bio.c
  bio/bio_lib.c
  bio/bf_nbio.c
  bio/bio_sock2.c
  bio/bio_print.c
  bio/bss_fd.c
  bio/bf_lbuf.c
  bio/bio_addr.c
  cmac/cmac.c
  pkcs12/p12_decr.c
  pkcs12/p12_crt.c
  pkcs12/p12_attr.c
  pkcs12/p12_p8d.c
  pkcs12/p12_p8e.c
  pkcs12/p12_init.c
  pkcs12/p12_kiss.c
  pkcs12/p12_mutl.c
  pkcs12/p12_utl.c
  pkcs12/p12_sbag.c
  pkcs12/p12_asn.c
  pkcs12/p12_key.c
  pkcs12/p12_crpt.c
  pkcs12/pk12err.c
  pkcs12/p12_add.c
  pkcs12/p12_npas.c
  chacha/chacha_enc.c
  chacha/chacha_ppc.c
  sm2/sm2_crypt.c
  sm2/sm2_key.c
  sm2/sm2_err.c
  sm2/sm2_sign.c
  LPdir_unix.c
  s390xcap.c
  crmf/crmf_err.c
  crmf/crmf_pbm.c
  crmf/crmf_asn.c
  crmf/crmf_lib.c
  self_test_core.c
  engine/eng_table.c
  engine/eng_ctrl.c
  engine/eng_pkey.c
  engine/tb_cipher.c
  engine/eng_fat.c
  engine/eng_err.c
  engine/eng_lib.c
  engine/eng_rdrand.c
  engine/tb_rsa.c
  engine/tb_dsa.c
  engine/tb_digest.c
  engine/eng_cnf.c
  engine/eng_init.c
  engine/eng_list.c
  engine/tb_dh.c
  engine/eng_openssl.c
  engine/tb_eckey.c
  engine/tb_rand.c
  engine/tb_asnmth.c
  engine/eng_all.c
  engine/tb_pkmeth.c
  engine/eng_dyn.c
  info.c
  sha/sha1dgst.c
  sha/sha256.c
  sha/keccak1600.c
  sha/sha3.c
  sha/sha_ppc.c
  sha/sha512.c
  sha/sha1_one.c
  params_from_text.c
  mem.c
  rc5/rc5_enc.c
  rc5/rc5cfb64.c
  rc5/rc5ofb64.c
  rc5/rc5_ecb.c
  rc5/rc5_skey.c
  der_writer.c
  x509/pcy_node.c
  x509/x509_v3.c
  x509/v3_prn.c
  x509/x509_cmp.c
  x509/v3_int.c
  x509/v3_utl.c
  x509/v3_ia5.c
  x509/v3_ist.c
  x509/v3_asid.c
  x509/v3_akeya.c
  x509/x509_trust.c
  x509/v3_genn.c
  x509/x_pubkey.c
  x509/x509name.c
  x509/v3_sxnet.c
  x509/pcy_cache.c
  x509/v3_ncons.c
  x509/by_dir.c
  x509/x509rset.c
  x509/v3_addr.c
  x509/x509_meth.c
  x509/x_x509a.c
  x509/v3_admis.c
  x509/x509spki.c
  x509/v3_cpols.c
  x509/x_crl.c
  x509/x_req.c
  x509/v3_extku.c
  x509/x509_lu.c
  x509/x_all.c
  x509/x509_ext.c
  x509/x509_att.c
  x509/by_store.c
  x509/x_attrib.c
  x509/x509_set.c
  x509/v3_info.c
  x509/x509cset.c
  x509/v3_bitst.c
  x509/v3_utf8.c
  x509/v3_akid.c
  x509/x509_def.c
  x509/by_file.c
  x509/v3_purp.c
  x509/x_x509.c
  x509/x509_req.c
  x509/t_x509.c
  x509/x509_vpm.c
  x509/pcy_map.c
  x509/v3_enum.c
  x509/v3_pmaps.c
  x509/v3_lib.c
  x509/x509_txt.c
  x509/x_exten.c
  x509/x509_r2x.c
  x509/pcy_data.c
  x509/v3_conf.c
  x509/x509_obj.c
  x509/x509_d2.c
  x509/v3_tlsf.c
  x509/x509type.c
  x509/x509_vfy.c
  x509/x509_err.c
  x509/v3_skid.c
  x509/v3_pcons.c
  x509/pcy_lib.c
  x509/x_name.c
  x509/v3_pci.c
  x509/v3_san.c
  x509/t_req.c
  x509/pcy_tree.c
  x509/t_crl.c
  x509/v3_crld.c
  x509/v3err.c
  x509/v3_pcia.c
  x509/v3_bcons.c
  x509/v3_pku.c
  core_namemap.c
  mdc2/mdc2dgst.c
  mdc2/mdc2_one.c
  poly1305/poly1305_ieee754.c
  poly1305/poly1305_ppc.c
  poly1305/poly1305_base2_44.c
  poly1305/poly1305.c
  ct/ct_x509v3.c
  ct/ct_sct_ctx.c
  ct/ct_prn.c
  ct/ct_sct.c
  ct/ct_oct.c
  ct/ct_policy.c
  ct/ct_vfy.c
  ct/ct_err.c
  ct/ct_b64.c
  ct/ct_log.c
  asn1_dsa.c
  ripemd/rmd_dgst.c
  ripemd/rmd_one.c
  context.c
)

if(UNIX)
	set(CRYPTO_SRC ${CRYPTO_SRC} crypto_lock.c)
	set(CRYPTO_SRC ${CRYPTO_SRC} bio/b_posix.c)
	set(CRYPTO_SRC ${CRYPTO_SRC} bio/bss_log.c)
	set(CRYPTO_SRC ${CRYPTO_SRC} ui/ui_openssl.c)
endif()


if(NOT HAVE_ASPRINTF)
	set(EXTRA_EXPORT ${EXTRA_EXPORT} asprintf)
	set(EXTRA_EXPORT ${EXTRA_EXPORT} vasprintf)
endif()

if(NOT HAVE_FREEZERO)
	set(EXTRA_EXPORT ${EXTRA_EXPORT} freezero)
endif()


if(NOT HAVE_REALLOCARRAY)
	set(EXTRA_EXPORT ${EXTRA_EXPORT} reallocarray)
endif()

if(NOT HAVE_RECALLOCARRAY)
	set(EXTRA_EXPORT ${EXTRA_EXPORT} recallocarray)
endif()

if(NOT HAVE_STRCASECMP)
	set(EXTRA_EXPORT ${EXTRA_EXPORT} strcasecmp)
endif()

if(NOT HAVE_STRLCAT)
	set(EXTRA_EXPORT ${EXTRA_EXPORT} strlcat)
endif()

if(NOT HAVE_STRLCPY)
	set(EXTRA_EXPORT ${EXTRA_EXPORT} strlcpy)
endif()

if(NOT HAVE_STRNDUP)
	set(EXTRA_EXPORT ${EXTRA_EXPORT} strndup)
	if(NOT HAVE_STRNLEN)
		set(EXTRA_EXPORT ${EXTRA_EXPORT} strnlen)
	endif()
endif()

if(NOT HAVE_STRSEP)
	set(EXTRA_EXPORT ${EXTRA_EXPORT} strsep)
endif()

if(NOT HAVE_SYSLOG_R)
endif()

if(NOT HAVE_TIMEGM)
	set(EXTRA_EXPORT ${EXTRA_EXPORT} timegm)
endif()

if(NOT HAVE_EXPLICIT_BZERO)
	set(EXTRA_EXPORT ${EXTRA_EXPORT} explicit_bzero)
endif()

if(NOT HAVE_ARC4RANDOM_BUF)
	set(EXTRA_EXPORT ${EXTRA_EXPORT} arc4random)
	set(EXTRA_EXPORT ${EXTRA_EXPORT} arc4random_buf)
	set(EXTRA_EXPORT ${EXTRA_EXPORT} arc4random_uniform)

	if(NOT HAVE_GETENTROPY)
		set(EXTRA_EXPORT ${EXTRA_EXPORT} getentropy)
	endif()
endif()

if(NOT HAVE_TIMINGSAFE_BCMP)
	set(EXTRA_EXPORT ${EXTRA_EXPORT} timingsafe_bcmp)
endif()

if(NOT HAVE_TIMINGSAFE_MEMCMP)
	set(EXTRA_EXPORT ${EXTRA_EXPORT} timingsafe_memcmp)
endif()

if(NOT ENABLE_ASM)
	add_definitions(-DOPENSSL_NO_ASM)
else()
	if(MSVC)
		if((NOT "${CMAKE_GENERATOR}" MATCHES "Win64") AND
		   (NOT "${CMAKE_GENERATOR_PLATFORM}" STREQUAL "x64"))
			add_definitions(-DOPENSSL_NO_ASM)
		endif()
	elseif(WIN32)
		add_definitions(-DOPENSSL_NO_ASM)
	endif()
endif()

if(NOT "${OPENSSLDIR}" STREQUAL "")
	add_definitions(-DOPENSSLDIR=\"${OPENSSLDIR}\")
else()
	if(WIN32)
		add_definitions(-DOPENSSLDIR=\"C:/Windows/libressl/ssl\")
	else()
		add_definitions(-DOPENSSLDIR=\"${CMAKE_INSTALL_PREFIX}/etc/ssl\")
	endif()
endif()

file(READ ${CMAKE_CURRENT_SOURCE_DIR}/crypto.sym SYMS)
foreach(SYM IN LISTS CRYPTO_UNEXPORT)
	string(REPLACE "${SYM}\n" "" SYMS ${SYMS})
endforeach()
file(WRITE ${CMAKE_CURRENT_BINARY_DIR}/crypto_p.sym ${SYMS})
if(EXTRA_EXPORT)
	list(SORT EXTRA_EXPORT)
	foreach(SYM IN LISTS EXTRA_EXPORT)
		file(APPEND ${CMAKE_CURRENT_BINARY_DIR}/crypto_p.sym "${SYM}\n")
	endforeach()
endif()

set(LIBTLS_EXTRA_EXPORT ${EXTRA_EXPORT} PARENT_SCOPE)

add_library(crypto_obj OBJECT ${CRYPTO_SRC})
target_include_directories(crypto_obj
	PRIVATE
		.
		asn1
		bn
		dsa
		ec
		ecdh
		ecdsa
		evp
		modes
	PUBLIC
		../include)

add_library(crypto $<TARGET_OBJECTS:crypto_obj>)
target_include_directories(crypto
	PRIVATE
		.
		asn1
		bn
		dsa
		ec
		ecdh
		ecdsa
		evp
		modes
	PUBLIC
		../include)

export_symbol(crypto ${CMAKE_CURRENT_BINARY_DIR}/crypto_p.sym)
target_link_libraries(crypto ${PLATFORM_LIBS})
if (WIN32)
	set(CRYPTO_POSTFIX -${CRYPTO_MAJOR_VERSION})
endif()
set_target_properties(crypto PROPERTIES
	OUTPUT_NAME crypto${CRYPTO_POSTFIX}
	ARCHIVE_OUTPUT_NAME crypto${CRYPTO_POSTFIX})
set_target_properties(crypto PROPERTIES VERSION
	${CRYPTO_VERSION} SOVERSION ${CRYPTO_MAJOR_VERSION})
