#
# Copyright (C) 2020 Lorenzo Zolfanelli
#
# This is free software, licensed under the GNU General Public License v3.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-lxc
PKG_VERSION:=3.0.4
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/lxc/python3-lxc/archive
PKG_HASH:=b282c6752a8961643f021c373dfa98d35de856093f28c68c017b367e1d0f64d8

PKG_LICENSE:=LGPL-2.1-or-later
PKG_LICENSE_FILES:=COPYING
PKG_MAINTAINER:=Lorenzo Zolfanelli <lorenzo.zolfanelli@gmail.com>

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-lxc-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python3-lxc/Default
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Python 3.x bindings for LXC API
  URL:=https://github.com/lxc/python3.lxc
endef

define Package/python3-lxc
$(call Package/python3-lxc/Default)
  DEPENDS:= \
      +PACKAGE_python3-lxc:python3-light \
      +PACKAGE_python3-lxc:liblxc
  VARIANT:=python3
endef

define Package/python3-lxc/description
Python 3.x bindings for the LXC container API.
endef

$(eval $(call Py3Package,python3-lxc))
$(eval $(call BuildPackage,python3-lxc))
$(eval $(call BuildPackage,python3-lxc-src))
