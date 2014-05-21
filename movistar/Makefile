#
# Copyright (C) 2014 Álvaro Fernández Rojas
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ftth-movistar
PKG_VERSION:=master
PKG_RELEASE=$(PKG_VERSION)

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_PROTO:=git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=git://github.com/openwrt-es/ftth-movistar.git
PKG_SOURCE_VERSION:=$(PKG_VERSION)

PKG_MAINTAINER:=Álvaro Fernández Rojas <noltari@gmail.com>

include $(INCLUDE_DIR)/package.mk

define Package/ftth-movistar
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=FTTH
  URL:=http://foro.seguridadwireless.net/openwrt/
  TITLE:=FTTH Movistar
  DEPENDS:=+kmod-bridge +swconfig +bird4 +mcproxy +udpxy +xupnpd
endef

define Build/Compile

endef

define Package/ftth-movistar/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/movistar.sh $(1)/usr/sbin/ftth-movistar
endef

$(eval $(call BuildPackage,ftth-movistar))
