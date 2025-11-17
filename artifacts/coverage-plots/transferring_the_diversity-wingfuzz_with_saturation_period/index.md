# 4.7 &ndash; Transferring the Diversity: WingFuzz (including Saturation Period)
Median of 10 trials starting from the corpus saturated by both LibAFL and libFuzzer, plots include 95% confidence interval.

The combined coverage of both libFuzzer and LibAFL is shown dashed. After the vertical line StorFuzz/LibAFL and WingFuzz/libFuzzer are run for 96 hours, starting with the merged corpora.

In some cases the coverage dips below the initial coverage from the seed set. This happens as both StorFuzz and WingFuzz discard parts of the seed set, which are identical to their coverage metrics, but not identical to the metric employed by llvm-cov. We believe this to be the result of differences in compiler optimizations.

 - LibAFL ![#98df8a](../.assets/98df8a.png)
 - libFuzzer ![#ff9896](../.assets/ff9896.png)
 - StorFuzz/LibAFL ![#d62728](../.assets/d62728.png)
 - WingFuzz/libFuzzer ![#ff7f0e](../.assets/ff7f0e.png)


## bloaty_fuzz_target
![bloaty_fuzz_target](./bloaty_fuzz_target_coverage_growth.svg)

## curl_curl_fuzzer_http
![curl_curl_fuzzer_http](./curl_curl_fuzzer_http_coverage_growth.svg)

## freetype2_ftfuzzer
![freetype2_ftfuzzer](./freetype2_ftfuzzer_coverage_growth.svg)

## harfbuzz_hb-shape-fuzzer
![harfbuzz_hb-shape-fuzzer](./harfbuzz_hb-shape-fuzzer_coverage_growth.svg)

## jsoncpp_jsoncpp_fuzzer
![jsoncpp_jsoncpp_fuzzer](./jsoncpp_jsoncpp_fuzzer_coverage_growth.svg)

## lcms_cms_transform_fuzzer
![lcms_cms_transform_fuzzer](./lcms_cms_transform_fuzzer_coverage_growth.svg)

## libjpeg-turbo_libjpeg_turbo_fuzzer
![libjpeg-turbo_libjpeg_turbo_fuzzer](./libjpeg-turbo_libjpeg_turbo_fuzzer_coverage_growth.svg)

## libpcap_fuzz_both
![libpcap_fuzz_both](./libpcap_fuzz_both_coverage_growth.svg)

## libpng_libpng_read_fuzzer
![libpng_libpng_read_fuzzer](./libpng_libpng_read_fuzzer_coverage_growth.svg)

## libxml2_xml
![libxml2_xml](./libxml2_xml_coverage_growth.svg)

## libxslt_xpath
![libxslt_xpath](./libxslt_xpath_coverage_growth.svg)

## mbedtls_fuzz_dtlsclient
![mbedtls_fuzz_dtlsclient](./mbedtls_fuzz_dtlsclient_coverage_growth.svg)

## openh264_decoder_fuzzer
![openh264_decoder_fuzzer](./openh264_decoder_fuzzer_coverage_growth.svg)

## openssl_x509
![openssl_x509](./openssl_x509_coverage_growth.svg)

## openthread_ot-ip6-send-fuzzer
![openthread_ot-ip6-send-fuzzer](./openthread_ot-ip6-send-fuzzer_coverage_growth.svg)

## proj4_proj_crs_to_crs_fuzzer
![proj4_proj_crs_to_crs_fuzzer](./proj4_proj_crs_to_crs_fuzzer_coverage_growth.svg)

## re2_fuzzer
![re2_fuzzer](./re2_fuzzer_coverage_growth.svg)

## sqlite3_ossfuzz
![sqlite3_ossfuzz](./sqlite3_ossfuzz_coverage_growth.svg)

## stb_stbi_read_fuzzer
![stb_stbi_read_fuzzer](./stb_stbi_read_fuzzer_coverage_growth.svg)

## systemd_fuzz-link-parser
![systemd_fuzz-link-parser](./systemd_fuzz-link-parser_coverage_growth.svg)

## vorbis_decode_fuzzer
![vorbis_decode_fuzzer](./vorbis_decode_fuzzer_coverage_growth.svg)

## woff2_convert_woff2ttf_fuzzer
![woff2_convert_woff2ttf_fuzzer](./woff2_convert_woff2ttf_fuzzer_coverage_growth.svg)

## zlib_zlib_uncompress_fuzzer
![zlib_zlib_uncompress_fuzzer](./zlib_zlib_uncompress_fuzzer_coverage_growth.svg)

