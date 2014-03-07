#
# Copyright (C) 2009-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=py-radix
PKG_VERSION:=0.5
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://py-radix.googlecode.com/files
PKG_MD5SUM:=8c853ce312b769de627d958a1cd6e5a0

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-radix
	SECTION:=lang-python
	CATEGORY:=Languages
	SUBMENU:=Python
	TITLE:=python-radix
	URL:=http://code.google.com/p/py-radix/
	DEPENDS:=+python
endef

define Package/python-radix/description
py-radix is an implementation of a radix tree for Python, which supports storage and lookups of IPv4 and IPv6 networks. This is a Python equivalent to Dave Plonka's Perl Net::Patricia (it even steals the same radix tree code from MRTd).
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/python-radix/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-radix))
