#
# Copyright (C) 2007-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=tc-viewer
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/jsalatiel/tc-viewer.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_VERSION=HEAD



PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	SECTION:=net
	CATEGORY:=Network
	SUBMENU:=Routing and Redirection
	TITLE:=Realtime monitoring for HTB/HFSC queues
	DEPENDS:=+perlbase-essential +perlbase-getopt +perlbase-file tc
endef

define Package/tc-viewer/description
	Realtime monitoring for HTB/HFSC queues
endef


define Build/Compile
endef

define Package/${PKG_NAME}/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_BUILD_DIR)/tc-viewer $(1)/usr/bin/
	$(CP) $(PKG_BUILD_DIR)/tc-alias $(1)/usr/bin/
endef

$(eval $(call BuildPackage,tc-viewer))
