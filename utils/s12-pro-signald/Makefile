include $(TOPDIR)/rules.mk

PKG_NAME:=s12-pro-signald
PKG_VERSION:=1.0.0
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define Package/s12-pro-signald
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=ZLT S12 Pro SignalD
  DEPENDS:=+sms-tool +uci
endef

define Package/s12-pro-signald/description
  Updates signal and modem LEDs on the ZLT S12 Pro based on LTE status, with UCI config support.
endef

define Build/Compile
  true
endef

define Package/s12-pro-signald/install
  $(INSTALL_DIR) $(1)/etc/init.d
  $(INSTALL_BIN) ./files/s12-pro-signald $(1)/etc/init.d/s12-pro-signald
  $(INSTALL_DIR) $(1)/sbin
  $(INSTALL_BIN) ./files/s12-pro-signal $(1)/sbin/s12-pro-signal
  $(INSTALL_BIN) ./files/update_s12_leds $(1)/sbin/update_s12_leds
  $(INSTALL_DIR) $(1)/etc/config
  $(INSTALL_CONF) ./files/s12ledsig $(1)/etc/config/s12ledsig
endef

$(eval $(call BuildPackage,s12-pro-signald))
