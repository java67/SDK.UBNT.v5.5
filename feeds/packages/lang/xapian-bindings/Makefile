#
# Copyright (C) 2008 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
# $Id: Makefile 12821 2008-10-02 15:33:26Z lars $

include $(TOPDIR)/rules.mk

PKG_NAME:=xapian-bindings
PKG_VERSION:=1.0.7
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://oligarchy.co.uk/xapian/$(PKG_VERSION)
PKG_FIXUP:=libtool

include $(INCLUDE_DIR)/package.mk
-include $(if $(DUMP),,$(STAGING_DIR)/mk/python-package.mk)

PKG_INSTALL=1

define Package/python-xapian
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=xapian python bindings
  URL:=http://oligarchy.co.uk/xapian/
  DEPENDS:=python +libxapian
endef

define Build/Configure
  $(call Build/Configure/Default, --with-python)
endef

define Package/python-xapian/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) $(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* $(1)$(PYTHON_PKG_DIR)
endef

$(eval $(call BuildPackage,python-xapian))


