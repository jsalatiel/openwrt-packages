include $(TOPDIR)/rules.mk

PKG_NAME:=perl-date-calc
PKG_VERSION:=6.3
PKG_RELEASE:=1
PKG_MD5SUM:=9b64555b7051c1beb6b61daead2d01b3

PKG_SOURCE_URL:=http://search.cpan.org/CPAN/authors/id/S/ST/STBEY/
PKG_SOURCE:=Date-Calc-6.3.tar.gz

PKG_BUILD_DIR:=$(BUILD_DIR)/perl/Date-Calc-6.3

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/perl/perlmod.mk

define Package/perl-date-calc
SUBMENU:=Perl
SECTION:=lang
CATEGORY:=Languages
TITLE:=Gregorian calendar date calculations
URL:=http://search.cpan.org/dist/Date-Calc/
DEPENDS:=perl
endef

define Build/Configure
	$(call perlmod/Configure,,)
endef

define Build/Compile
	$(call perlmod/Compile,,)
endef

define Package/perl-date-calc/install
	$(call perlmod/Install,$(1),Date auto)
endef


$(eval $(call BuildPackage,perl-date-calc))
