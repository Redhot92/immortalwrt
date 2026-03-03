include $(TOPDIR)/rules.mk

PKG_NAME:=openvpn-openssl
PKG_VERSION:=2.6.9
PKG_RELEASE:=1

PKG_SOURCE:=openvpn-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://swupdate.openvpn.org/community/releases/
PKG_HASH:=SKIP

include $(INCLUDE_DIR)/package.mk

define Package/openvpn-openssl
  SECTION:=net
  CATEGORY:=Network
  TITLE:=OpenVPN with XOR scramble
  DEPENDS:=+libopenssl
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	tar xzf $(DL_DIR)/$(PKG_SOURCE) -C $(PKG_BUILD_DIR) --strip-components=1
endef

define Package/openvpn-openssl/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/openvpn $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,openvpn-openssl))
