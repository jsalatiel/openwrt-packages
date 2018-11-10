include $(TOPDIR)/rules.mk


PKG_NAME:=perl-net-ssleay
PKG_REV:=493
PKG_VERSION:=r$(PKG_REV)
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=svn://svn.debian.org/svn/net-ssleay/trunk
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=svn


PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

export OPENSSL_PREFIX=$(shell ls -1d $(BUILD_DIR)/openssl* )

include $(INCLUDE_DIR)/package.mk

include $(TOPDIR)/feeds/packages/lang/perl/perlmod.mk

define Package/perl-net-ssleay
	SUBMENU:=Perl
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Perl extension for using OpenSSL
	DEPENDS:=perl +libopenssl +zlib +perlbase-thread +perlbase-base +perlbase-net +perl-io-socket-ssl +perl-date-calc +perl-carp-clan
	URL:=http://search.cpan.org/dist/Net-SSLeay
endef

define Build/Configure
	$(call perlmod/Configure,,)
endef

define Build/Compile
	(sed -i -e "/^LDDLFLAGS/s/'//g" -e "/^CCFLAGS/s/'//g"  $(PKG_BUILD_DIR)/Makefile)
	$(call perlmod/Compile,,)
endef

define Package/perl-net-ssleay/install
	$(call perlmod/Install,$(1),Net auto)
endef


$(eval $(call BuildPackage,perl-net-ssleay))
