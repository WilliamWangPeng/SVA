dnl
dnl Configure script for SVA
dnl
AC_INIT([SVA], [1.0], [jtcriswel@gmail.com])

dnl
dnl Define enable options for SVA-OS
dnl

dnl Enable the Virutal Ghost features
AC_ARG_ENABLE(vg,
              AS_HELP_STRING([--enable-vg],
                             [Enable Virtual Ghost (default is NO)]),
                             [case "${enableval}" in
                             	yes) AC_DEFINE(VG) ;;
                             	no)  AC_DEFINE(NOVG) ;;
                             	*)   AC_MSG_ERROR([bad value ${enableval} for --enable-vg]) ;;
                             esac],
                             AC_DEFINE(NOVG))

dnl Enable Ghost Memory allocation randomization
AC_ARG_ENABLE(vg-random,
              AS_HELP_STRING([--enable-vg-random],
                             [Enable Ghost Memory allocation randomization (default is NO)]),
                             [case "${enableval}" in
                             	yes) AC_DEFINE(VG_RANDOM) ;;
                             	no)  AC_DEFINE(NOVG_RANDOM) ;;
                             	*)   AC_MSG_ERROR([bad value ${enableval} for --enable-vg]) ;;
                             esac],
                             AC_DEFINE(NOVG_RANDOM))

dnl Enable the use of MPX for SFI
AC_ARG_ENABLE(mpx,
              AS_HELP_STRING([--enable-mpx],
                             [Enable MPX for SFI (default is NO)]),
                             [case "${enableval}" in
                             	yes) AC_DEFINE(MPX)
                                   AC_SUBST([COPTFLAGS], ["-mllvm -enable-mpx-sfi -no-integrated-as"])
                                   ;;
                             	no)  AC_DEFINE(NOMPX)
                                   AC_SUBST([COPTFLAGS], [""])
                                   ;;
                             	*)   AC_MSG_ERROR([bad value ${enableval} for --enable-mpx]) ;;
                             esac],
                             AC_DEFINE(NOMPX))

dnl Enable the SVA MMU Checks
AC_ARG_ENABLE(mmuchecks,
              AS_HELP_STRING([--enable-mmuchecks],
                             [Enable SVA MMU Checks (default is YES)]),
                             [case "${enableval}" in
                             	yes) AC_DEFINE(CHECKMMU) ;;
                             	no)  AC_DEFINE(NOCHECKMMU) ;;
                             	*)   AC_MSG_ERROR([bad value ${enableval} for --enable-mmuchecks]) ;;
                             esac],
                             AC_DEFINE(CHECKMMU))

dnl Enable SVA Direct Map Enhancement
AC_ARG_ENABLE(sva-dmap,
              AS_HELP_STRING([--enable-sva-dmap],
                             [Enable SVA Direct Map Feature (default is NO)]),
                             [case "${enableval}" in
                             	yes) AC_DEFINE(SVA_DMAP) ;;
                             	no)  AC_DEFINE(NOSVA_DMAP) ;;
                             	*)   AC_MSG_ERROR([bad value ${enableval} for --enable-sva-dmap]) ;;
                             esac],
                             AC_DEFINE(NOSVA_DMAP))

dnl Enable SVA ASID Feature
AC_ARG_ENABLE(asid,
              AS_HELP_STRING([--enable-asid],
                             [Enable SVA ASID Feature (default is NO)]),
                             [case "${enableval}" in
                             	yes) AC_DEFINE(SVA_ASID_PG) ;;
                             	no)  AC_DEFINE(NOSVA_ASID_PG) ;;
                             	*)   AC_MSG_ERROR([bad value ${enableval} for --enable-sva-dmap]) ;;
                             esac],
                             AC_DEFINE(NOSVA_ASID_PG))

dnl Enable LLC partitioning Feature
AC_ARG_ENABLE(llc-part,
              AS_HELP_STRING([--enable-llc-part],
                             [Enable SVA LLC partitioning Feature (default is NO)]),
                             [case "${enableval}" in
                              yes) AC_DEFINE(SVA_LLC_PART) ;;
                              no)  AC_DEFINE(NOSVA_LLC_PART) ;;
                              *)   AC_MSG_ERROR([bad value ${enableval} for --enable-llc-part]) ;;
                             esac],
                             AC_DEFINE(NOSVA_LLC_PART))

dnl Enable Defenses Against Page Table Side-channels
AC_ARG_ENABLE(pg-defenses,
              AS_HELP_STRING([--enable-pg-defenses],
                             [Enable defenses against page table side-channels (default is NO)]),
                             [case "${enableval}" in
                              yes) AC_DEFINE(SVA_PG_DEF) ;;
                              no)  AC_DEFINE(NOSVA_PG_DEF) ;;
                              *)   AC_MSG_ERROR([bad value ${enableval} for --enable-llc-part]) ;;
                             esac],
                             AC_DEFINE(NOSVA_PG_DEF))


dnl
dnl Include the command-line option to configure the targets used by LLVM
dnl
AC_ARG_ENABLE([targets], [], [], [])

dnl
dnl Specify header files that need to be configured by configure
dnl
AC_CONFIG_HEADERS([SVA/include/sva/asmconfig.h])

dnl
dnl Specify the files that will need to be configured
dnl
AC_CONFIG_FILES([make.conf])

dnl
dnl Configure the SVA LLVM compiler
dnl
AC_CONFIG_SUBDIRS([llvm])

dnl
dnl Generate the output of the configure script
dnl
AC_OUTPUT
