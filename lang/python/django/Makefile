#
# Copyright (C) Alexandru Ardelean <ardeleanalex@gmail.com>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=django
PKG_VERSION:=3.2.15
PKG_RELEASE:=$(AUTORELEASE)

PYPI_NAME:=Django
PKG_HASH:=f71934b1a822f14a86c9ac9634053689279cd04ae69cb6ade4a59471b886582b

PKG_MAINTAINER:=Alexandru Ardelean <ardeleanalex@gmail.com>, Peter Stadler <peter.stadler@student.uibk.ac.at>
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE LICENSE.python
PKG_CPE_ID:=cpe:/a:djangoproject:django

include ../pypi.mk
include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-django
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=The web framework for perfectionists with deadlines.
  URL:=https://www.djangoproject.com/
  DEPENDS:= +python3 +python3-pytz +python3-sqlparse +python3-asgiref
  CONFLICTS:=python3-django1
  PROVIDES:=django
endef

define Package/python3-django/description
    The web framework for perfectionists with deadlines.
endef

define Py3Package/python3-django/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/django-admin.py \
		$(1)/usr/bin/django-admin
endef

$(eval $(call Py3Package,python3-django))
$(eval $(call BuildPackage,python3-django))
$(eval $(call BuildPackage,python3-django-src))
