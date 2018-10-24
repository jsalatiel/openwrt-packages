#
# Copyright (C) 2006-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.

include $(TOPDIR)/rules.mk

PKG_NAME:=noip-duc

PKG_VERSION:=2
PKG_RELEASE:=1
#PKG_MD5SUM:=3b0f5f2ff8637c73ab337be403252a60


PKG_SOURCE:=noip-duc-linux.tar.gz
PKG_SOURCE_URL:=http://www.no-ip.com/client/linux/
PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=COPYING

PKG_BUILD_DIR:=$(BUILD_DIR)/noip-2/

include $(INCLUDE_DIR)/package.mk


UNPACK_CMD=tar --strip-components=1 -C $(1) -xf "$(DL_DIR)/$(PKG_SOURCE)" 

define Build/Prepare
        $(PKG_UNPACK)
        $(Build/Patch)
endef



define Package/noip-duc
	TITLE:=no-ip dynamic update client
	SECTION:=net
	CATEGORY:=Network
	SUBMENU:=IP Addresses and Names
endef

define Package/noip-duc/description
No-ip dynamic update client
endef


define Package/noip-duc/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/noip2 $(1)/usr/bin/noip2
endef

$(eval $(call BuildPackage,noip-duc))
