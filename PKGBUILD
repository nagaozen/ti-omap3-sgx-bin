# Maintainer: Joni Lapilainen <joni.lapilainen@gmail.com>

# PVR SGX 530 core revision (r121 or r125).
_sgxrev="r121"
# Path to hardware specific library dir.
_hwlibs="/usr/lib/v7l/neon"

pkgname=ti-omap3-sgx-bin
pkgver=1.4.268
pkgrel=3
arch=('armv7h')
url="https://build.pub.meego.com/package/show?package=ti-omap3-sgx&project=CE%3AAdaptation%3AN9xx-common"
depends=('mesa' 'libxext' 'libxfixes')
makedepends=('chrpath')
replaces=('libegl-pvr' 'libgles-pvr' 'libpvr' 'pvr-bin')
license=('Custom')
options=('!strip')
install=ti-omap3-sgx-bin.install
backup=('etc/powervr.ini')

source=('powervr.ini' 'powervr.service'
https://api.pub.meego.com/public/source/CE:Adaptation:N9xx-common/ti-omap3-sgx/${pkgname}-${pkgver}-armv7hl.tar.bz2)

md5sums=('9f485c5662d06c3c2fefae7bac481f1e'
         '04f53c56ca696262cc2f777bb6228930'
         '844928cd623fd37533edcec2ce8b020f')

package() {

  pkgdesc='PowerVR SGX libraries and tools for OMAP3 (Nokia version)'

  install -D -m 644 ${srcdir}/powervr.ini \
   ${pkgdir}/etc/powervr.ini
  install -D -m 644 ${srcdir}/powervr.service \
   ${pkgdir}/usr/lib/systemd/system/powervr.service
  install -D -m 744 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/sbin/pvrsrvinit_${_sgxrev} \
   ${pkgdir}/usr/sbin/pvrsrvinit
  chrpath -d ${pkgdir}/usr/sbin/pvrsrvinit

  install -D -m 755 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/lib/libEGL_${_sgxrev}.so \
   ${pkgdir}/${_hwlibs}/libEGL.so.${pkgver}
  install -D -m 755 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/lib/libGLES_CM_${_sgxrev}.so \
   ${pkgdir}/${_hwlibs}/libGLES_CM.so.${pkgver}
  install -D -m 755 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/lib/libGLESv2_${_sgxrev}.so \
   ${pkgdir}/${_hwlibs}/libGLESv2.so.${pkgver}
  install -D -m 755 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/lib/libIMGegl_${_sgxrev}.so \
   ${pkgdir}/${_hwlibs}/libIMGegl.so.${pkgver}
  install -D -m 755 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/lib/libOpenVGU_${_sgxrev}.so \
   ${pkgdir}/${_hwlibs}/libOpenVGU.so.${pkgver}
  install -D -m 755 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/lib/libOpenVG_${_sgxrev}.so \
   ${pkgdir}/${_hwlibs}/libOpenVG.so.${pkgver}
  install -D -m 755 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/lib/libglslcompiler_${_sgxrev}.so \
   ${pkgdir}/${_hwlibs}/libglslcompiler.so.${pkgver}
  install -D -m 755 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/lib/libpvr2d_${_sgxrev}.so \
   ${pkgdir}/${_hwlibs}/libpvr2d.so.${pkgver}
  install -D -m 755 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/lib/libsrv_um_${_sgxrev}.so \
   ${pkgdir}/${_hwlibs}/libsrv_um.so.${pkgver}
  install -D -m 755 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/lib/libPVRScopeServices_${_sgxrev}.so \
   ${pkgdir}/${_hwlibs}/libPVRScopeServices.so.${pkgver}
  install -D -m 755 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/lib/libpvrPVR2D_BLITWSEGL_${_sgxrev}.so \
   ${pkgdir}/${_hwlibs}/libpvrPVR2D_BLITWSEGL.so.${pkgver}
  install -D -m 755 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/lib/libpvrPVR2D_DRI2WSEGL_${_sgxrev}.so \
   ${pkgdir}/${_hwlibs}/libpvrPVR2D_DRI2WSEGL.so.${pkgver}
  install -D -m 755 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/lib/libpvrPVR2D_FLIPWSEGL_${_sgxrev}.so \
   ${pkgdir}/${_hwlibs}/libpvrPVR2D_FLIPWSEGL.so.${pkgver}
  install -D -m 755 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/lib/libpvrPVR2D_FRONTWSEGL_${_sgxrev}.so \
   ${pkgdir}/${_hwlibs}/libpvrPVR2D_FRONTWSEGL.so.${pkgver}
  install -D -m 755 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/lib/libpvrPVR2D_X11WSEGL_${_sgxrev}.so \
   ${pkgdir}/${_hwlibs}/libpvrPVR2D_X11WSEGL.so.${pkgver}

  install -d ${pkgdir}/usr/include/SGX/EGL/ ${pkgdir}/usr/include/SGX/GLES/ \
   ${pkgdir}/usr/include/SGX/GLES2/ ${pkgdir}/usr/include/SGX/KHR/ \
   ${pkgdir}/usr/include/SGX/include4/ ${pkgdir}/usr/include/SGX/hwdefs/

  install -m 644 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/include/pvr2d.h \
   ${pkgdir}/usr/include/
  install -m 644 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/include/EGL/* \
   ${pkgdir}/usr/include/SGX/EGL/
  install -m 644 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/include/GLES/* \
   ${pkgdir}/usr/include/SGX/GLES/
  install -m 644 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/include/GLES2/* \
   ${pkgdir}/usr/include/SGX/GLES2/
  install -m 644 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/include/KHR/* \
   ${pkgdir}/usr/include/SGX/KHR/
  install -m 644 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/include/SGX/include4/* \
   ${pkgdir}/usr/include/SGX/include4/
  install -m 644 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/include/SGX/hwdefs/* \
   ${pkgdir}/usr/include/SGX/hwdefs/

  install -D -m 644 \
   ${srcdir}/${pkgname}-${pkgver}-armv7hl/usr/share/doc/${pkgname}-${pkgver}/license.txt \
   ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE

  cd ${pkgdir}/${_hwlibs}
  chrpath -k -d ./*.so.${pkgver}
  ln -s libEGL.so.${pkgver} libEGL.so.1.0.0
  ln -s libEGL.so.${pkgver} libEGL.so.1
  ln -s libEGL.so.${pkgver} libEGL.so
  ln -s libGLES_CM.so.${pkgver} libGLES_CM.so.1
  ln -s libGLES_CM.so.${pkgver} libGLES_CM.so
  ln -s libGLES_CM.so.${pkgver} libGLESv1_CM.so.1.1.0
  ln -s libGLES_CM.so.${pkgver} libGLESv1_CM.so.1
  ln -s libGLES_CM.so.${pkgver} libGLESv1_CM.so
  ln -s libGLESv2.so.${pkgver} libGLESv2.so.2.0.0
  ln -s libGLESv2.so.${pkgver} libGLESv2.so.2
  ln -s libGLESv2.so.${pkgver} libGLESv2.so
  ln -s libIMGegl.so.${pkgver} libIMGegl.so
  ln -s libOpenVGU.so.${pkgver} libOpenVGU.so
  ln -s libOpenVG.so.${pkgver} libOpenVG.so
  ln -s libglslcompiler.so.${pkgver} libglslcompiler.so
  ln -s libpvr2d.so.${pkgver} libpvr2d.so
  ln -s libsrv_um.so.${pkgver} libsrv_um.so
  ln -s libPVRScopeServices.so.${pkgver} libPVRScopeServices.so
  ln -s libpvrPVR2D_BLITWSEGL.so.${pkgver} libpvrPVR2D_BLITWSEGL.so
  ln -s libpvrPVR2D_DRI2WSEGL.so.${pkgver} libpvrPVR2D_DRI2WSEGL.so
  ln -s libpvrPVR2D_FLIPWSEGL.so.${pkgver} libpvrPVR2D_FLIPWSEGL.so
  ln -s libpvrPVR2D_FRONTWSEGL.so.${pkgver} libpvrPVR2D_FRONTWSEGL.so
  ln -s libpvrPVR2D_X11WSEGL.so.${pkgver} libpvrPVR2D_X11WSEGL.so
}
