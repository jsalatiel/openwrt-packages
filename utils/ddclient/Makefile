#
# Copyright (C) 2007-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ddclient
PKG_VERSION:=3.8.3
PKG_RELEASE:=1
#PKG_LICENSE:=GPL-3.0+
#PKG_LICENSE_FILES:=COPYING

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=@SF/ddclient
PKG_MD5SUM:=e17c0a37a1d140f682fdb85d3050fd7d

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	SECTION:=net
	CATEGORY:=Network
	SUBMENU:=IP Addresses and Names
	TITLE:=Perl client used to update dynamic DNS
	DEPENDS:=+perl +perlbase-essential  +perlbase-net +perlbase-sys +perlbase-getopt +perl-carp-clan +perl-date-calc +perl-io-socket-ssl +perl-net-ssleay +perl-xml-simple +perlbase-perlio +perlbase-autoloader
endef

define Package/ddclient/description
	ddclient is a Perl client used to update dynamic DNS entries for accounts on Dynamic DNS Network Service Provider. 
endef


define Build/Compile
endef

define Package/${PKG_NAME}/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_DIR) $(1)/etc/config
	$(CP) $(PKG_BUILD_DIR)/ddclient $(1)/usr/bin/
	$(CP) ./files/ddclient.init $(1)/etc/init.d/ddclient
	$(CP) ./files/ddclient.config $(1)/etc/config/ddclient

endef

$(eval $(call BuildPackage,ddclient))

