include $(TOPDIR)/rules.mk

PKG_NAME:=perl-io-socket-ssl
#PKG_VERSION:=2.020
PKG_VERSION:=2.037
PKG_RELEASE:=1

PKG_SOURCE:=IO-Socket-SSL-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://search.cpan.org/CPAN/authors/id/S/SU/SULLR
#PKG_MD5SUM:=dc0f5992492786a0bde79d2f8fb00cc1
PKG_MD5SUM:=415172849bcc03a1f59ea012233ad127
PKG_BUILD_DIR:=$(BUILD_DIR)/perl/IO-Socket-SSL-$(PKG_VERSION)


include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/perl/perlmod.mk

define Package/perl-io-socket-ssl
  SUBMENU:=Perl
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=SSL sockets with IO::Socket interface
  URL:=http://search.cpan.org/dist/IO-Socket-SSL/
  DEPENDS:=perl +libopenssl
endef


define Build/Configure
	$(call perlmod/Configure,,)
endef

define Build/Compile
	$(call perlmod/Compile,,)
endef

define Package/perl-io-socket-ssl/install
	$(call perlmod/Install,$(1),IO auto)
endef


$(eval $(call BuildPackage,perl-io-socket-ssl))
