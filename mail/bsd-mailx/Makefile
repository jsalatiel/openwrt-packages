#
# Copyright (C) 2007-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=bsd-mailx
PKG_VERSION:=8.1.2-0.20100314cvs.orig

PKG_SOURCE:=$(PKG_NAME)_$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://ftp.debian.org/debian/pool/main/b/bsd-mailx/

PKG_MD5SUM:=cb73caa586f96cd6fe9c717b327e19a4

include $(INCLUDE_DIR)/package.mk

TARGET_CFLAGS += $(TARGET_CPPFLAGS)

define Package/bsd-mailx
  SECTION:=mail
  CATEGORY:=Mail
  DEPENDS:=+libopenssl +liblockfile
  TITLE:=Simple command-line-mode mail user agent
  URL:=http://packages.debian.org/bsd-mailx
endef

define Package/bsd-mailx/description
bsd-mailx is the traditional simple command-line-mode mail user agent. Even if you don't use it,
it may be required by other programs.
The /usr/bin/mail command provided by this package is a very simple one, and does not include many
features that can be found in more advanced mail user agents.
For example bsd-mailx DOES NOT support:
	 - MIME           (i.e. no attachments, no UTF-8 or other charsets support);
	 - SMTP protocol  (/usr/sbin/sendmail interface only is used);
	 - POP3/IMAP      (bsd-mailx reads local mailboxes only);
	 - maildir format (traditional mbox only format is supported).
endef

CONFIGURE_VARS += \
	LIBS="$(TARGET_LDFLAGS) -lcrypto -llock"

define Package/bsd-mailx/install
        $(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mail $(1)/usr/bin/bsd-mailx
endef


$(eval $(call BuildPackage,bsd-mailx))
