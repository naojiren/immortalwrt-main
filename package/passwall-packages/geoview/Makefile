include $(TOPDIR)/rules.mk

PKG_NAME:=geoview
PKG_VERSION:=0.2.6
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-linux-arm64
PKG_SOURCE_URL:=https://github.com/snowie2000/geoview/releases/download/$(PKG_VERSION)/
PKG_HASH:=f7250e82b0e688a2c535cdd4e935a953c41926490d7c48a970c68a2023d5e6d7
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_LICENSE:=Apache-2.0
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=snowie2000

include $(INCLUDE_DIR)/package.mk

define Package/geoview
  TITLE:=A geofile toolkit
  URL:=https://github.com/snowie2000/geoview
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=IP Addresses and Names
  DEPENDS:=@aarch64
endef

define Package/geoview/description
  geoview is a handy tool to extract useful information from geo* files.
endef

define Build/Prepare
	$(INSTALL_DIR) $(PKG_BUILD_DIR)
	$(CP) $(DL_DIR)/$(PKG_SOURCE) $(PKG_BUILD_DIR)/geoview
endef

define Build/Compile
endef

define Package/geoview/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/geoview $(1)/usr/bin/geoview
endef

$(eval $(call BuildPackage,geoview))
