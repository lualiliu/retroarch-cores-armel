# retroarch-cores-armel

Some Libretro core for retroarch adapted to the ARMel (older 32-bit ARM EABI Soft Float) architecture.

If you can compile ppsspp core, please contact me.


# retroarch compile note

configure

`CFLAGS="$CFLAGS -O3 -fno-tree-vectorize -DMESA_EGL_NO_X11_HEADERS" ./configure --disable-vg \
                           --disable-sdl \
                           --disable-sdl2 \
                           --disable-ssl \
                           --enable-zlib \
                           --enable-freetype \
                           --enable-translate \
                           --enable-cdrom \
                           --enable-command \
                           --disable-kms \
                           --enable-egl \
                           --enable-opengles --disable-kms --disable-x11 --enable-mali_fbdev \
--datarootdir=${SYSROOT_PREFIX}/usr/share`

make

`make V=1 \
                      HAVE_LAKKA=1 \
                      HAVE_LAKKA_PROJECT="${DEVICE:-${PROJECT}}.${ARCH}" \
                      HAVE_LAKKA_SERVER="${LAKKA_UPDATE_SERVER_URL}" \
                      HAVE_CHEEVOS=1 \
                      HAVE_HAVE_ZARCH=0 \
                      HAVE_WIFI=1 \
                      HAVE_BLUETOOTH=1 \
                      HAVE_FREETYPE=1
`
