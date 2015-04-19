#
# Copyright (C) 2014-2015 Álvaro Fernández Rojas
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
  DEPENDS:= +kmod-bridge +swconfig
    DEPENDS+= +FTTH_MOVISTAR_SERV_DDNS:ddns-scripts +FTTH_MOVISTAR_SERV_WOL:etherwake +FTTH_MOVISTAR_SERV_UPNP:miniupnpd
  DEPENDS+= +FTTH_MOVISTAR_VOIP:bird4
  DEPENDS+= +FTTH_MOVISTAR_IPTV:bird4 +FTTH_MOVISTAR_IPTV_IGMPPROXY:igmpproxy +FTTH_MOVISTAR_IPTV:kmod-ipt-nathelper-rtsp +FTTH_MOVISTAR_IPTV_MCPROXY:mcproxy
    DEPENDS+= +FTTH_MOVISTAR_IPTV_UDPXY:udpxy +FTTH_MOVISTAR_IPTV_XUPNPD:xupnpd
  DEPENDS+= +FTTH_MOVISTAR_LUCI:luci +FTTH_MOVISTAR_LUCI:luci-proto-ipv6
    DEPENDS+= +FTTH_MOVISTAR_LUCI_DDNS:luci-app-ddns +FTTH_MOVISTAR_LUCI_UDPXY:luci-app-udpxy +FTTH_MOVISTAR_LUCI_UPNP:luci-app-upnp +FTTH_MOVISTAR_LUCI_WOL:luci-app-wol
endef

define Package/ftth-movistar/config
	source "$(SOURCE)/Config.in"
endef

define Build/Compile

endef

define Package/ftth-movistar/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/movistar.sh $(1)/usr/sbin/ftth-movistar
endef

$(eval $(call BuildPackage,ftth-movistar))
