include $(TOPDIR)/rules.mk

PKG_NAME:=botocore
PKG_VERSION:=1.12.66
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/b/botocore
PKG_HASH:=25c39ecc71356287cf79d66981ec77deca374e28043b19b2f818d48aa34272a1
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-botocore-$(PKG_VERSION)

PKG_MAINTAINER:=Daniel Danzberger <daniel@dd-wrt.com>
PKG_LICENSE:=MIT

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-botocore/Default
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=botocore
  URL:=https://github.com/boto/botocore
endef

define Package/python-botocore
$(call Package/python-botocore/Default)
  DEPENDS:=+python \
	+python-urllib3 \
	+python-docutils \
	+python-dateutil \
	+python-jmespath \
	+python-requests
  VARIANT:=python
endef

define Package/python3-botocore
$(call Package/python-botocore/Default)
  DEPENDS:=+python3 \
	+python3-urllib3 \
	+python3-docutils \
	+python3-dateutil \
	+python3-jmespath \
	+python3-requests
  VARIANT:=python3
endef

define Package/python-botocore/description
A low-level interface to a growing number of Amazon Web Services.
The botocore package is the foundation for the AWS CLI as well as boto3.
endef

define Package/python3-botocore/description
$(call Package/python-botocore/description)
.
(Variant for Python3)
endef

$(eval $(call PyPackage,python-botocore))
$(eval $(call BuildPackage,python-botocore))
$(eval $(call BuildPackage,python-botocore-src))

$(eval $(call Py3Package,python3-botocore))
$(eval $(call BuildPackage,python3-botocore))
$(eval $(call BuildPackage,python3-botocore-src))
