
include $(TOPDIR)/rules.mk

PKG_NAME:=tcpstat
PKG_VERSION:=1.5
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)_$(PKG_VERSION).orig.tar.gz
PKG_SOURCE_URL:=http://deb.debian.org/debian/pool/main/t/tcpstat/
PKG_HASH:=46fde9458cc5678264b0c5f2197f84ada9101951197fdeec5f04b0801fcff0ba

PKG_LICENSE:=BSD-1-Clause
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/tcpstat
  SECTION:=net
  CATEGORY:=Network
  URL:=https://frenchfries.net/paul/tcpstat/
  MAINTAINER:=Jonas Jelonek <jelonek.jonas@gmail.com>
  TITLE:=network interface statistics reporting tool
  DEPENDS:=+libpcap
endef

define Package/tcpstat/description
  tcpstat reports certain network interface statistics much like
  vmstat does for system statistics. tcpstat gets its information
  by either monitoring a specific interface or by reading previously
  saved tcpdump data from a file.

  Some of the statistics tcpstat calculates:
      - bandwidth
      - number of packets
      - packets per second
      - average packet size
      - standard deviation of packet size
      - interface load
      - more...

  tcpstat is written with performance and efficiency in mind and is
  capable of handling large amounts of packets per second. Its compact
  command line interface is geared for the network researcher, system
  administrator and desktop shell user. tcpstat has been a valuable
  tool in university research papers and commercial network alike.
endef

define Package/tcpstat/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/tcpstat $(1)/usr/bin/
endef

$(eval $(call BuildPackage,tcpstat))
