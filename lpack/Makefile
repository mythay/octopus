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

PKG_NAME:=lpack
PKG_VERSION:=0.0.1
PKG_RELEASE:=1
PKG_LICENSE:=MIT

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/LuaDist/lpack.git
PKG_SOURCE_VERSION:=master
PKG_SOURCE_PROTO:=git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)


PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/lpack
  CATEGORY:=easyon
  TITLE:=lpack
  URL:=https://github.com/LuaDist/lpack
  DEPENDS:= +lua
endef

define Package/lpack/description
	A library for packing and unpacking binary data. The library adds two functions to the string library: pack and unpack. http://www.tecgraf.puc-rio.br/~lhf/ftp/lua/#lpack
endef

CMAKE_OPTIONS += \
	-DCMAKE_VERBOSE_MAKEFILE=ON

define Package/lpack/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/pack.so $(1)/usr/lib/lua/

#        $(INSTALL_DIR) $(1)/usr/lib/lua/lpack
#        $(INSTALL_DATA) $(PKG_BUILD_DIR)/lua/lpack/util.lua $(1)/usr/lib/lua/lpack
endef

$(eval $(call BuildPackage,lpack))