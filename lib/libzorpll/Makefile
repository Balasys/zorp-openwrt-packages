#
# Copyright (C) 2014-2015 BalaBit IT Security
# Copyright (C) 2015-2016 Balasys
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=libzorpll
PKG_VERSION:=6.0.8.0

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/balasys/libzorpll.git
PKG_SOURCE_SUBDIR:=libzorpll
PKG_SOURCE_VERSION:=9a695821fd13a1a86a3556f4516e4e9e564091fa
PKG_SOURCE_PROTO:=git

PKG_LICENSE:=LGPLv2

PKG_INSTALL:=1
PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

PKG_MAINTAINER:=Szilárd Pfeiffer <coroner@balasys.hu>

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk

define Package/libzorpll
	CATEGORY:=Libraries
	SUBMENU:=Firewall
	TITLE:=libzorpll
	DEPENDS:= +libstdcpp +glib2 +libopenssl +zlib +libcap
endef

define Build/Configure
	(cd $(PKG_BUILD_DIR); ./autogen.sh)
	$(call Build/Configure/Default)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr
	$(CP) $(PKG_INSTALL_DIR)/usr/* $(1)/usr/
endef

define Package/libzorpll/install
	$(INSTALL_DIR) $(1)/usr
	$(CP) $(PKG_INSTALL_DIR)/usr/* $(1)/usr/
endef

$(eval $(call BuildPackage,libzorpll))
