#
# Copyright (C) 2009-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pbr
PKG_VERSION:=0.10.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/p/pbr/
PKG_MD5SUM:=9e02dbfb5e49210c381fd4eea00cf7b7

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/pbr
	SECTION:=lang-python
	CATEGORY:=Languages
	SUBMENU:=Python
	TITLE:=pbr
	URL:=https://pypi.python.org/pypi/pbr
	DEPENDS:=+python
endef

define Package/pbr/description
PBR is a library that injects some useful and sensible default behaviors
into your setuptools run.
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/pbr/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,pbr))
