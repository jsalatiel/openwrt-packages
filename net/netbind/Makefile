#
# Copyright (C) 2007-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk



PKG_NAME:=netbind
PKG_VERSION:=1.1
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/jsalatiel/$(PKG_NAME).git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_VERSION=HEAD

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	SECTION:=net
	CATEGORY:=Network
	TITLE:=netbind
endef

define Build/Compile
	$(call Build/Compile/Default,FOO=bar) 
endef

define Package/$(PKG_NAME)/description
	Binds app to specific interface
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/local/bin
	$(INSTALL_DIR) $(1)/usr/local/lib/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/netbind $(1)/usr/local/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bind.so $(1)/usr/local/lib/
endef


$(eval $(call BuildPackage,$(PKG_NAME)))

