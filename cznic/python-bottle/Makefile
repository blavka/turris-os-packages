#
# Copyright (C) 2013 CZ.NIC z.s.p.o. <jan.cermak@nic.cz>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=bottle
PKG_VERSION:=0.11.6
PKG_RELEASE:=1

PKG_SOURCE:=bottle-0.11.6.tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/b/bottle/
PKG_MD5SUM:=0bafdc4e13ea2b1a3bddf36b5af108c4

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-bottle
	SUBMENU:=Python
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=python-bottle
	URL:=http://bottlepy.org
	DEPENDS:=+python
	MAINTAINER:=Jan Cermak <jan.cermak@nic.cz>
endef

define Package/python-bottle/description
	Fast and simple WSGI-framework for small web-applications.
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/python-bottle/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)
endef

$(eval $(call BuildPackage,python-bottle))