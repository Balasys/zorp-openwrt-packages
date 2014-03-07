#
# Copyright (C) 2014-2015 BalaBit IT Security
# Copyright (C) 2015-2016 Balasys
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=zorp-iptables-addons
PKG_VERSION:=6.0.1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/balasys/$(PKG_NAME).git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_SOURCE_VERSION:=c4b509e74c9c0cd49b2065de5a48c5be63969286
PKG_SOURCE_PROTO:=git

PKG_LICENSE:=GPLv2

PKG_INSTALL:=1
PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

PKG_MAINTAINER:=Szilárd Pfeiffer <coroner@balasys.hu>

include $(INCLUDE_DIR)/package.mk

define Package/zorp-iptables-addons
	SECTION:=net
	CATEGORY:=Network
	TITLE:=Zorp IPTables addons
	DEPENDS:= +libxtables
endef

define Build/Configure
	(cd $(PKG_BUILD_DIR); ./autogen.sh)
	$(call Build/Configure/Default)
endef

define Package/zorp-iptables-addons/install
	$(INSTALL_DIR) $(1)/usr/lib/iptables
	$(CP) $(PKG_BUILD_DIR)/extensions/libxt_*.so $(1)/usr/lib/iptables/
endef

$(eval $(call BuildPackage,zorp-iptables-addons,+libxtables))
