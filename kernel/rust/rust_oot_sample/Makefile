
include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=rust-oot-sample
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define KernelPackage/rust-oot-sample
  SUBMENU:=Other modules
  TITLE:=Rust Out-Of-Tree Sample Module
  FILES:=$(PKG_BUILD_DIR)/rust_out_of_tree.ko
endef

define KernelPackage/rust-oot-sample/description
Rust out-of-tree sample module
endef

include $(INCLUDE_DIR)/kernel-defaults.mk

define Build/Compile
	$(KERNEL_MAKE) M="$(PKG_BUILD_DIR)" modules
endef

$(eval $(call KernelPackage,rust-oot-sample))
