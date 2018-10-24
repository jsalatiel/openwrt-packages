#
# Copyright (C) 2007-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk



PKG_NAME:=ykush
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/Yepkit/ykush.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_VERSION=HEAD



PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

# compile using uclibc++
#include $(INCLUDE_DIR)/uclibc++.mk

define Package/$(PKG_NAME)
	SECTION:=utils
	CATEGORY:=Utilities
	TITLE:=YKUSH Board Control Application
# compile using uclibc++
#	DEPENDS:=+hidapi $(CXX_DEPENDS)
# compile using stcdp=+
	DEPENDS:=+hidapi +libstdcpp
endef

define Package/ykush/description
	Control application for Yepkit YKUSH Switchable USB Hub board.
endef

define Package/ykush/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/ykushcmd $(1)/usr/bin/
endef


$(eval $(call BuildPackage,ykush))

