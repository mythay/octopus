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

PKG_NAME:=luv
PKG_VERSION:=1.6.1
PKG_RELEASE:=1
PKG_LICENSE:=Apache 2.0

PKG_SOURCE:=$(PKG_NAME)-v$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/luvit/luv/releases/download/v1.6.1/
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-v$(PKG_VERSION)
PKG_MD5SUM:=a17671dfb478e8b6a155115331d1873d

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-v$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/luv
  CATEGORY:=easyon
  TITLE:=luv
  URL:=https://github.com/luvit/luv
  DEPENDS:=+lua +libpthread +librt
endef

define Package/luv/description
	libuv bindings for luajit and lua 5.1/5.2.
endef


CMAKE_OPTIONS += \
	-DWITH_LUA_ENGINE=Lua -DLUA_BUILD_TYPE=System


define Package/luv/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/luv.so $(1)/usr/lib/lua/

#        $(INSTALL_DIR) $(1)/usr/lib/lua/luv
#        $(INSTALL_DATA) $(PKG_BUILD_DIR)/lua/luv/util.lua $(1)/usr/lib/lua/luv
endef

$(eval $(call BuildPackage,luv))