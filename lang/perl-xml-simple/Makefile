include $(TOPDIR)/rules.mk

PKG_NAME:=perl-xml-simple
PKG_VERSION:=2.22
PKG_RELEASE:=1
PKG_MD5SUM:=0914abddfce749453ed89b54029f2643
PKG_SOURCE_URL:=http://search.cpan.org/CPAN/authors/id/G/GR/GRANTM/
PKG_SOURCE:=XML-Simple-$(PKG_VERSION).tar.gz

PKG_BUILD_DIR:=$(BUILD_DIR)/perl/XML-Simple-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/perl/perlmod.mk

define Package/perl-xml-simple
SUBMENU:=Perl
SECTION:=lang
CATEGORY:=Languages
TITLE:=Simple Date
URL:=http://search.cpan.org/dist/XML-Simple/
DEPENDS:=perl
endef

define Build/Configure
	$(call perlmod/Configure,,)
endef

define Build/Compile
	$(call perlmod/Compile,,)
endef

define Package/perl-xml-simple/install
	$(call perlmod/Install,$(1),XML auto)
endef


$(eval $(call BuildPackage,perl-xml-simple))
