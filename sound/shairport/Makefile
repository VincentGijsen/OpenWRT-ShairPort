#
# Copyright (C) 2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=shairport-trunk
PKG_VERSION:=trunk
PKG_RELEASE:=$(PKG_SOURCE_VERSION)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git://github.com/VincentGijsen/shairport
PKG_SOURCE_VERSION:=master
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk


define Package/shairport-trunk/Default
  SECTION:=sound
  CATEGORY:=Sound
  TITLE:=ShairPort-trunk
  URL:=http://mafipulation.org/
endef


define Package/shairport-trunk
  $(Package/shairport-trunk/Default)
  DEPENDS:= +libopenssl +alsa-lib
endef

define Package/shairport-trunk/description
  Shairport TRUNK version, use TINYSVCMDNS
endef


define Package/shairport-trunk/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/shairport $(1)/usr/bin/
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_BIN) ./files/init.d/airplay $(1)/etc/init.d/
	$(INSTALL_DATA) ./files/config/airplay $(1)/etc/config/
	$(INSTALL_DATA) ./files/asound.conf $(1)/etc/
endef


$(eval $(call BuildPackage,shairport-trunk))
