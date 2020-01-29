#
# Copyright (C) Anders Thomson
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.

include $(TOPDIR)/rules.mk

PKG_NAME:=libbs
PKG_SOURCE_VERSION:=c59b0b44e29307335fd561ba954ac360d31c95f5
PKG_VERSION:=2020-01-26-$(PKG_SOURCE_VERSION)
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/andersthomson/libbs.git
PKG_MAINTAINER:=Anders Thomson
PKG_LICENSE:=BSD-3

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)

PKG_FIXUP:=autoreconf


include $(INCLUDE_DIR)/package.mk
#include $(INCLUDE_DIR)/cmake.mk

define Package/libbs
  SECTION:=utils
  CATEGORY:=utils
  SUBMENU:=utils
  TITLE:=Blinkstick library and cli
  URL:=https://github.com/andersthomson/libbs/
  DEPENDS+=+libusb-1.0
endef

define Package/libbs/description
 This package provides a library and cli to interface with blinkstick USB LEDs.
endef

define Build/Configure
	$(call Build/Configure/Default,)
endef

define Package/libbs/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/.libs/bs $(1)/usr/bin/

	$(INSTALL_DIR) $(1)/usr/lib/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/.libs/libbs.so.0.0.0 $(1)/usr/lib/libbs.so.0
endef

$(eval $(call BuildPackage,libbs))
