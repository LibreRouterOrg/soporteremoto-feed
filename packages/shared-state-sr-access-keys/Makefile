#
# Copyright (C) 2020 German Ferrero <germanferrero@altermundi.net>
#
# This is free software, licensed under the GNU Affero General Public License v3.
#

include $(TOPDIR)/rules.mk

GIT_COMMIT_DATE:=$(shell git log -n 1 --pretty=%ad --date=short . )
GIT_COMMIT_TSTAMP:=$(shell git log -n 1 --pretty=%at . )

PKG_NAME:=shared-state-sr-access-keys
PKG_VERSION=$(GIT_COMMIT_DATE)-$(GIT_COMMIT_TSTAMP)

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	TITLE:=remote support access keys module for shared-state
	CATEGORY:=SoporteRemoto
	MAINTAINER:=German Ferrero <germanferrero@altermundi.net>
	URL:=http://librerouter.org
	DEPENDS:=+@BUSYBOX_CONFIG_ASH_RANDOM_SUPPOR +lua +luci-lib-jsonc \
			shared-state
	PKGARCH:=all
endef

define Package/$(PKG_NAME)/description
	Syncronize SoporteRemoto access keys beween nodes.
endef

define Build/Compile
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/
	$(CP) ./files/* $(1)/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
