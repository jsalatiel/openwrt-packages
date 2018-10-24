#
# Copyright (C) 2006-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.

include $(TOPDIR)/rules.mk

PKG_NAME:=nmap-mini

PKG_VERSION:=5.51
PKG_RELEASE:=4
PKG_MD5SUM:=0b80d2cb92ace5ebba8095a4c2850275

PKG_MAINTAINER=Nuno Goncalves <nunojpg@gmail.com>

PKG_SOURCE:=nmap-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=http://nmap.org/dist/
PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=COPYING

PKG_INSTALL:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/nmap-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

NMAP_DEPENDS:=+libpcap +libstdcpp

define Package/nmap-mini/default
  SUBMENU:=NMAP Suite
  SECTION:=net
  CATEGORY:=Network
  URL:=http://nmap.org/
endef

define Package/nmap-mini
$(call Package/nmap-mini/default)
  DEPENDS:=$(NMAP_DEPENDS)
  TITLE:=Mini version no-ssl 
endef

CONFIGURE_ARGS += \
	--with-libdnet=included \
	--with-libpcre=included \
	--with-libpcap="$(STAGING_DIR)/usr" \
	--without-liblua \
	--without-zenmap --without-openssl

CONFIGURE_VARS += CXXFLAGS="$$$$CXXFLAGS -fno-builtin"

define Package/nmap-mini/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/nmap $(1)/usr/bin/nmap-mini
	$(INSTALL_DIR) $(1)/usr/share/nmap
	$(CP) $(PKG_INSTALL_DIR)/usr/share/nmap/* $(1)/usr/share/nmap/
endef

$(eval $(call BuildPackage,nmap-mini))
