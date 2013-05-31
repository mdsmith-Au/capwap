# 
# Copyright (C) 2009 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
# $Id: Makefile $

# OpenWrt package for Open Source CAPWAP
# Prepared by Michael Smith, McGill University

include $(TOPDIR)/rules.mk

PKG_NAME_SHORT:=capwap
PKG_NAME:=$(PKG_NAME_SHORT)

PKG_RELEASE:=1
PKG_VERSION=0.93.3

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/capwap/Default
	SECTION:=net
	CATEGORY:=Network
endef

define Package/capwap/Default/description
	The project is an implementation of CAPWAP agents for WTPs and ACs.
endef

define Package/capwap
	$(call Package/capwap/Default)
	TITLE:=open source capwap
	DEPENDS:=+libopenssl +libpthread
endef

define Package/capwap/description
	$(call Package/capwap/Default/description)
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./capwap-0.93.3/* $(PKG_BUILD_DIR)/
endef

define Package/capwap/install
	$(INSTALL_DIR) $(1)/usr/capwap/
#	$(INSTALL_DATA) $(PKG_BUILD_DIR)/* $(1)/usr/capwap/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/AC $(1)/usr/capwap/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/WTP $(1)/usr/capwap/
endef

$(eval $(call BuildPackage,capwap))
