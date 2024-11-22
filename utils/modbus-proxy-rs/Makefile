# SPDX-License-Identifier: GPL-2.0-only
#
# Copyright (C) 2024 Jonas Jelonek

include $(TOPDIR)/rules.mk

PKG_NAME:=modbus-proxy-rs
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/jonasjelonek/modbus-proxy-rs.git
PKG_SOURCE_DATE:=2024-10-01
PKG_SOURCE_VERSION:=996b538fcdf53473e12467319934b048059dbd6c
PKG_MIRROR_HASH:=d2b3daac6243323ff008b543f4ec326b757617d884fd9f974a42ea486d408ff5

PKG_MAINTAINER:=Jonas Jelonek <jelonek.jonas@gmail.com>

PKG_BUILD_DEPENDS:=rust/host

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/rust/rust-package.mk

define Package/modbus-proxy-rs
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=modbus-proxy-rs - Modbus TCP/IP multiplexer
  DEPENDS:=$(RUST_ARCH_DEPENDS)
  URL:=https://github.com/tiagocoutinho/modbus-proxy-rs
endef

define Package/modbus-proxy-rs/description
  modbus-proxy-rs allows multiple Modbus TCP/IP clients to connect
  to one Modbus TCP/IP server that only allows one connection at a
  time (often the case with PV inverters).
endef

define Package/modbus-proxy-rs/install
	$(INSTALL_DIR) $(1)/usr/bin/ $(1)/etc/init.d/ 
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/bin/* $(1)/usr/bin/ 
	$(INSTALL_BIN) ./files/modbus-proxy-rs.init $(1)/etc/init.d/modbus-proxy-rs 
endef

$(eval $(call RustBinPackage,modbus-proxy-rs))
$(eval $(call BuildPackage,modbus-proxy-rs))
