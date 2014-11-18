#
# Copyright (C) 2014-2015 OpenWrt.org
# Copyright (C) 2014-2015 Szilárd Pfeiffer
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pydns
PKG_VERSION:=2.3.6
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/p/pydns/
PKG_MD5SUM:=e9574b74f01111405815a5fdccec15ce

PKG_MAINTAINER:=Szilárd Pfeiffer <coroner@pfeifferszilard.hu>
PKG_LICENSE:=Apache
PKG_LICENSE_FILES:=/LICENSE

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/pydns
	SECTION:=lang-python
	CATEGORY:=Languages
	SUBMENU:=Python
	TITLE:=pydns
	URL:=https://pypi.python.org/pypi/pydns
	DEPENDS:=+python +libcap
endef

define Package/pydns/description
Python DNS library
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/pydns/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,pydns))
