include $(TOPDIR)/rules.mk

PKG_NAME:=sing-box
PKG_VERSION:=1.13.19
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-linux-arm64-musl.tar.gz
PKG_SOURCE_URL:=https://github.com/SagerNet/sing-box/releases/download/v$(PKG_VERSION)/
PKG_HASH:=5146181884310ea2381e085ef504005c81bd09f80721542127efb0a73f12cd2f
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)-linux-arm64-musl

PKG_LICENSE:=GPL-3.0-or-later
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=SagerNet

include $(INCLUDE_DIR)/package.mk

define Package/sing-box
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=Web Servers/Proxies
  TITLE:=The universal proxy platform
  URL:=https://sing-box.sagernet.org/
  DEPENDS:=@aarch64 +ca-bundle +kmod-inet-diag +kmod-netlink-diag
endef

define Package/sing-box/description
  Official SagerNet static ARM64 musl build of sing-box.
endef

define Build/Compile
endef

define Package/sing-box/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/sing-box $(1)/usr/bin/sing-box
endef

$(eval $(call BuildPackage,sing-box))
