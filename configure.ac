# Version starts with 0 to facilitate actual upstream releases, in the future
# followed by the latest upstream svn revision number, followed by this
# autotools repackaging version.
#
# This number is bumped before the version is released, so to find the actual
# revision that creates that relase just look for the v$(version) tag.
AC_INIT([playfun], [0.2675.0], [https://github.com/gerow/playfun])
AC_CONFIG_MACRO_DIR([m4])
AM_INIT_AUTOMAKE([-Wall -Werror foreign subdir-objects])
AC_PROG_CXX
AM_PROG_AR
LT_INIT
# We require C++11
AX_CXX_COMPILE_STDCXX_11(,[mandatory])
PKG_CHECK_MODULES([SDL], [sdl])
PKG_CHECK_MODULES([SDL_NET], [SDL_net])
PKG_CHECK_MODULES([ZLIB], [zlib])
PKG_CHECK_MODULES([LIBPNG], [libpng])
PKG_CHECK_MODULES([PROTOBUF], [protobuf])
AC_CHECK_PROG([PROTOC], [protoc], [protoc])
AS_IF([test "x${PROTOC}" == "x"],
    [AC_MSG_ERROR([ProtoBuf compiler "protoc" not found.])])

AC_CONFIG_FILES([Makefile
		 cc-lib/Makefile
		 tasbot/Makefile])
AC_OUTPUT
