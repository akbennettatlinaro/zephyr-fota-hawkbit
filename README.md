#Linaro Firmware Over The Air Programming Example

Example application that uses Hawkbit to implement FOTA.

##Build Status:
| platforms | zephyr/master | zephyr/master-upstream-dev |
| --- | :---: | :---: |
| 96b_carbon | [![Build Status](http://ci.arm64.io:8080/buildStatus/icon?job=linaro-fota-hawkbit/PLATFORM=96b_carbon,ZEPHYR_SOURCE=zephyr-master)](https://ci.arm64.io/job/linaro-fota-hawkbit/PLATFORM=96b_carbon,ZEPHYR_SOURCE=zephyr-master/) | [![Build Status](http://ci.arm64.io:8080/buildStatus/icon?job=linaro-fota-hawkbit/PLATFORM=96b_carbon,ZEPHYR_SOURCE=zephyr-master-upstream-dev)](https://ci.arm64.io/job/linaro-fota-hawkbit/PLATFORM=96b_carbon,ZEPHYR_SOURCE=zephyr-master-upstream-dev/) |
| 96b_nitrogen | [![Build Status](http://ci.arm64.io:8080/buildStatus/icon?job=linaro-fota-hawkbit/PLATFORM=96b_nitrogen,ZEPHYR_SOURCE=zephyr-master)](https://ci.arm64.io/job/linaro-fota-hawkbit/PLATFORM=96b_nitrogen,ZEPHYR_SOURCE=zephyr-master/) | [![Build Status](http://ci.arm64.io:8080/buildStatus/icon?job=linaro-fota-hawkbit/PLATFORM=96b_nitrogen,ZEPHYR_SOURCE=zephyr-master-upstream-dev)](https://ci.arm64.io/job/linaro-fota-hawkbit/PLATFORM=96b_nitrogen,ZEPHYR_SOURCE=zephyr-master-upstream-dev/) |
| fdrm_k64f | [![Build Status](http://ci.arm64.io:8080/buildStatus/icon?job=linaro-fota-hawkbit/PLATFORM=frdm_k64f,ZEPHYR_SOURCE=zephyr-master)](https://ci.arm64.io/job/linaro-fota-hawkbit/PLATFORM=frdm_k64f,ZEPHYR_SOURCE=zephyr-master/) | [![Build Status](http://ci.arm64.io:8080/buildStatus/icon?job=linaro-fota-hawkbit/PLATFORM=frdm_k64f,ZEPHYR_SOURCE=zephyr-master-upstream-dev)](https://ci.arm64.io/job/linaro-fota-hawkbit/PLATFORM=frdm_k64f,ZEPHYR_SOURCE=zephyr-master-upstream-dev/) |

####Dependencies
View the build status of this project's [dependencies](dependencies.md)

##Requirements:
  * Newt's bootloader
  * Hawkbit server

##Board compatibility:

###nRF52
  * PCA10040
  * Nitrogen

##Creating and signing the image:

Check https://collaborate.linaro.org/display/LTD/IoT+Device for
the complete overview.


Quick example (Nitrogen; run this from zephyr-utils):


`./zep2newt.py --bin <zephyr-fota-hawkbit>/outdir/96b_nitrogen/zephyr.bin \
	      --key root.pem --sig RSA --vtoff 0x100 --out zephyr.img.bin`


Then just upload zephyr.img.bin to the Hawkbit server.

###TODO
  * Extend readme explaining how to setup the server environment
  * Explain how the FOTA process work
  * How to build and use newt's bootloader
  * OpenSSL support
  * Add support to use Hawkbit's security token when updating the server
