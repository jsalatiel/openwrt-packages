# 
# Copyright (C) 2006 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk


PKG_NAME:=liblockfile
PKG_VERSION:=1.08

PKG_SOURCE:=$(PKG_NAME)_$(PKG_VERSION).orig.tar.gz
PKG_SOURCE_URL:=http://ftp.debian.org/debian/pool/main/libl/liblockfile/

PKG_MD5SUM:=c24e2dfb4a2aab0263fe5ac1564d305e

PKG_LICENSE:=GPLv3
PKG_LICENSE_FILES:=COPYING

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/liblockfile
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=Support binaries for utilities based on liblockfile
  URL:=https://packages.debian.org/jessie/liblockfile-bin
endef

define Package/liblockfile/description
This package contains support binaries for the liblockfile library, and the command-line utility ``dotlockfile''. 
endef

CONFIGURE_ARGS+= \
        --enable-shared \
        --enable-static \

TARGET_CPPFLAGS:=-I. -I.. $(TARGET_CPPFLAGS)

TARGET_CFLAGS += $(FPIC)

define Build/Compile
	$(MAKE) $(PKG_JOBS) -C $(PKG_BUILD_DIR) \
		DESTDIR="$(PKG_INSTALL_DIR)" \
		all
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_BUILD_DIR)/lockfile.h $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/liblockfile.so $(1)/usr/lib/liblockfile.so
	ln -s $(1)/usr/lib/liblockfile.so $(1)/usr/lib/liblockfile.so.1
endef

define Package/liblockfile/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/liblockfile.so $(1)/usr/lib/liblockfile.so.1
endef

$(eval $(call BuildPackage,liblockfile))
