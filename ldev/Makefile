#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ldev
PKG_VERSION:=0.0.1
PKG_RELEASE:=1
PKG_LICENSE:=MIT

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/mythay/ldev.git
PKG_SOURCE_VERSION:=master
PKG_SOURCE_PROTO:=git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)


PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/ldev
  CATEGORY:=easyon
  TITLE:=ldev
  URL:=https://github.com/mythay/ldev
  DEPENDS:= +lua
endef

define Package/ldev/description
	ldev  for luv.
endef

CMAKE_OPTIONS += \
	-DCMAKE_VERBOSE_MAKEFILE=ON

define Package/ldev/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/ldev.so $(1)/usr/lib/lua/

#        $(INSTALL_DIR) $(1)/usr/lib/lua/ldev
#        $(INSTALL_DATA) $(PKG_BUILD_DIR)/lua/ldev/util.lua $(1)/usr/lib/lua/ldev
endef

$(eval $(call BuildPackage,ldev))