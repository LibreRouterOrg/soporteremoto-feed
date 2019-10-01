#
# Copyright (C) 2019 LibreMesh
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=luatweetnacl
PKG_VERSION:=0.5-1
PKG_RELEASE:=2
PKG_MAINTAINER:=Marcs Gutierrez <gmarcos87@gmail.com>
PKG_LICENSE:=LGPL-2.1+

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_MIRROR_HASH:=50adef58dc683516e88fa767939399b4ddeedb00
PKG_SOURCE_VERSION:=$(PKG_MIRROR_HASH)
PKG_SOURCE_URL:=https://github.com/gmarcos87/luatweetnacl.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_SUBDIR=$(PKG_NAME)-$(PKG_VERSION)

PKGARCH:=all
PKG_LICENSE_FILES:=COPYING
PKG_BUILD_DEPENDS:=lua

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=$(PKG_NAME)
	DEPENDS:=+liblua
	URL:=https://github.com/gmarcos87/luatweetnacl
endef

define Package/$(PKG_NAME)/description
	Lua binding to NaCl crypto library by Dan Bernstein
endef

MAKE_FLAGS += \
	FPIC="$(FPIC)" \
	CFLAGS="$(TARGET_CFLAGS)" \
	LDFLAGS="$(TARGET_LDFLAGS)"

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(CP) $(PKG_BUILD_DIR)/*.so $(1)/usr/lib/lua/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
