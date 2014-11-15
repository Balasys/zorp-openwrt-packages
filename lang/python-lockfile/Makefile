#
# Copyright (C) 2014-2015 OpenWrt.org
# Copyright (C) 2014-2015 Szilárd Pfeiffer
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=lockfile
PKG_VERSION:=0.8
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/l/lockfile
PKG_MD5SUM:=9dadf1554ac5bb0574fa565a20c2ad61

PKG_MAINTAINER:=Szilárd Pfeiffer <coroner@pfeifferszilard.hu>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=/LICENSE

PKG_BUILD_DEPENDS:=python-setuptools

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/lockfile
	SECTION:=lang-python
	CATEGORY:=Languages
	SUBMENU:=Python
	TITLE:=lockfile
	URL:=https://pypi.python.org/pypi/lockfile
	DEPENDS:=+python +bitarray
endef

define Package/lockfile/description
The lockfile package exports a LockFile class which provides a simple API for
locking files. Unlike the Windows msvcrt.locking function, the fcntl.lockf
and flock functions, and the deprecated posixfile module, the API is identical
across both Unix (including Linux and Mac) and Windows platforms.
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/lockfile/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,lockfile))
