include $(TOPDIR)/rules.mk

PKG_NAME:=perl-carp-clan
PKG_VERSION:=6.0.4
PKG_RELEASE:=1
PKG_MD5SUM:=b6316bc51bb530d994f2784615939fb2
PKG_SOURCE_URL:=http://search.cpan.org/CPAN/authors/id/S/ST/STBEY/
PKG_SOURCE:=Carp-Clan-6.04.tar.gz

PKG_BUILD_DIR:=$(BUILD_DIR)/perl/Carp-Clan-6.04


include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/perl/perlmod.mk

define Package/perl-carp-clan
	SUBMENU:=Perl
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Report errors from modules
	URL:=http://search.cpan.org/dist/Carp-Clan/
	DEPENDS:=perl
endef

define Build/Configure
	$(call perlmod/Configure,,)
endef

define Build/Compile
	$(call perlmod/Compile,,)
endef

define Package/perl-carp-clan/install
	$(call perlmod/Install,$(1),Carp auto)
endef


$(eval $(call BuildPackage,perl-carp-clan))
