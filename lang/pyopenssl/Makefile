#
# Copyright (C) 2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pyOpenSSL
PKG_VERSION:=0.14
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/p/pyOpenSSL/
PKG_MD5SUM:=8579ff3a1d858858acfba5f046a4ddf7

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/pyopenssl
	SECTION:=lang-python
	CATEGORY:=Languages
	SUBMENU:=Python
	TITLE:=pyopenssl
	URL:=https://github.com/pyca/pyopenssl
	DEPENDS:=+python +libopenssl
endef

define Package/pyopenssl/description
Python openssl library
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/pyopenssl/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,pyopenssl))
