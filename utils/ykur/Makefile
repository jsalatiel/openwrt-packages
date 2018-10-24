#
# Copyright (C) 2007-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk



PKG_NAME:=ykur
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/Yepkit/ykurcmd.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_VERSION=HEAD

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	SECTION:=utils
	CATEGORY:=Utilities
	TITLE:=YKUR Relay board control application
	DEPENDS:=+hidapi +libstdcpp
endef

define Build/Compile
#	rm $(PKG_BUILD_DIR)/ykurcmd/bin/ykurcmd $(PKG_BUILD_DIR)/ykurcmd/objs/*.o
	( cd $(PKG_BUILD_DIR) && make clean )
	$(call Build/Compile/Default,FOO=bar) 
endef

define Package/ykur/description
	Control utility for Yepkit YKUR USB Relay board.
endef

define Package/ykur/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/ykurcmd/bin/ykurcmd $(1)/usr/bin/
endef


$(eval $(call BuildPackage,ykur))

