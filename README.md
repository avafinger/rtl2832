# rtl2832 patch

This is a patch for DVB-T / DVB-C devices that use rtl2832u chipset (Rafael Micro r820t as an example).
There is a ton of tuners int this patch that may or may not work.
This patch has been applied against kernel version 3.4.103 and armbian legacy kernel 3.4.111.
The driver should work on A10 / A20 / H3 devices.

Applying the patch (diff patch)
==================

* clone this repo
git clone https://github.com/avafinger/rtl2832.git

* move the rtl2832.patch to:
linux-sunxi (a10/a20) or h3-wip (H3)

* run:
patch -p1 < ./rtl2832.patch
patching file drivers/media/dvb/dvb-usb/demod_rtl2832.c
patching file drivers/media/dvb/dvb-usb/demod_rtl2832.h
patching file drivers/media/dvb/dvb-usb/demod_rtl2836.c
patching file drivers/media/dvb/dvb-usb/demod_rtl2836.h
patching file drivers/media/dvb/dvb-usb/demod_rtl2840.c
patching file drivers/media/dvb/dvb-usb/demod_rtl2840.h
patching file drivers/media/dvb/dvb-usb/dtmb_demod_base.c
patching file drivers/media/dvb/dvb-usb/dtmb_demod_base.h
patching file drivers/media/dvb/dvb-usb/dtmb_nim_base.c
patching file drivers/media/dvb/dvb-usb/dtmb_nim_base.h
patching file drivers/media/dvb/dvb-usb/dvbt_demod_base.c
patching file drivers/media/dvb/dvb-usb/dvbt_demod_base.h
patching file drivers/media/dvb/dvb-usb/dvbt_nim_base.c
patching file drivers/media/dvb/dvb-usb/dvbt_nim_base.h
patching file drivers/media/dvb/dvb-usb/foundation.c
patching file drivers/media/dvb/dvb-usb/foundation.h
patching file drivers/media/dvb/dvb-usb/i2c_bridge.h
patching file drivers/media/dvb/dvb-usb/math_mpi.c
patching file drivers/media/dvb/dvb-usb/math_mpi.h
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_e4000.c
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_e4000.h
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_fc0012.c
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_fc0012.h
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_fc0013.c
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_fc0013.h
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_fc2580.c
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_fc2580.h
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_max3543.c
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_max3543.h
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_mt2063.c
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_mt2063.h
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_mt2266.c
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_mt2266.h
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_mxl5007t.c
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_mxl5007t.h
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_r820t.c
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_r820t.h
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_tda18272.c
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_tda18272.h
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_tua9001.c
patching file drivers/media/dvb/dvb-usb/nim_rtl2832_tua9001.h
patching file drivers/media/dvb/dvb-usb/nim_rtl2836_fc2580.c
patching file drivers/media/dvb/dvb-usb/nim_rtl2836_fc2580.h
patching file drivers/media/dvb/dvb-usb/nim_rtl2836_mxl5007t.c
patching file drivers/media/dvb/dvb-usb/nim_rtl2836_mxl5007t.h
patching file drivers/media/dvb/dvb-usb/nim_rtl2840_max3543.c
patching file drivers/media/dvb/dvb-usb/nim_rtl2840_max3543.h
patching file drivers/media/dvb/dvb-usb/nim_rtl2840_mt2063.c
patching file drivers/media/dvb/dvb-usb/nim_rtl2840_mt2063.h
patching file drivers/media/dvb/dvb-usb/qam_demod_base.c
patching file drivers/media/dvb/dvb-usb/qam_demod_base.h
patching file drivers/media/dvb/dvb-usb/qam_nim_base.c
patching file drivers/media/dvb/dvb-usb/qam_nim_base.h
patching file drivers/media/dvb/dvb-usb/rtl2832u_audio.c
patching file drivers/media/dvb/dvb-usb/rtl2832u_audio.h
patching file drivers/media/dvb/dvb-usb/rtl2832u.c
patching file drivers/media/dvb/dvb-usb/rtl2832u_fe.c
patching file drivers/media/dvb/dvb-usb/rtl2832u_fe.h
patching file drivers/media/dvb/dvb-usb/rtl2832u.h
patching file drivers/media/dvb/dvb-usb/rtl2832u_io.c
patching file drivers/media/dvb/dvb-usb/rtl2832u_io.h
patching file drivers/media/dvb/dvb-usb/tuner_base.h
patching file drivers/media/dvb/dvb-usb/tuner_e4000.c
patching file drivers/media/dvb/dvb-usb/tuner_e4000.h
patching file drivers/media/dvb/dvb-usb/tuner_fc0012.c
patching file drivers/media/dvb/dvb-usb/tuner_fc0012.h
patching file drivers/media/dvb/dvb-usb/tuner_fc0013.c
patching file drivers/media/dvb/dvb-usb/tuner_fc0013.h
patching file drivers/media/dvb/dvb-usb/tuner_fc2580.c
patching file drivers/media/dvb/dvb-usb/tuner_fc2580.h
patching file drivers/media/dvb/dvb-usb/tuner_max3543.c
patching file drivers/media/dvb/dvb-usb/tuner_max3543.h
patching file drivers/media/dvb/dvb-usb/tuner_mt2063.c
patching file drivers/media/dvb/dvb-usb/tuner_mt2063.h
patching file drivers/media/dvb/dvb-usb/tuner_mt2266.c
patching file drivers/media/dvb/dvb-usb/tuner_mt2266.h
patching file drivers/media/dvb/dvb-usb/tuner_mxl5007t.c
patching file drivers/media/dvb/dvb-usb/tuner_mxl5007t.h
patching file drivers/media/dvb/dvb-usb/tuner_r820t.c
patching file drivers/media/dvb/dvb-usb/tuner_r820t.h
patching file drivers/media/dvb/dvb-usb/tuner_tda18272.c
patching file drivers/media/dvb/dvb-usb/tuner_tda18272.h
patching file drivers/media/dvb/dvb-usb/tuner_tua9001.c
patching file drivers/media/dvb/dvb-usb/tuner_tua9001.h
patching file drivers/media/dvb/dvb-usb/Kconfig
patching file drivers/media/dvb/dvb-usb/Makefile

* remove the patch
rm ./rtl2832.patch

* config the kernel
enter menuconfig and set support for DVB_USB_RTL2832U or edit .config and manually add CONFIG_DVB_USB_RTL2832U

* rebuild the kernel
If everything is OK and you get a kernel image , this patch did not break anything! :)

* reboot and plug in your device, you should see something like in dmesg:
Rafael Micro r820t successfully identified

* if you build the driver as a module you should load the module:
modprobe modprobe dvb_usb_rtl2832u or add it to /etc/modules

This is known to work with some digital radio stick. 



