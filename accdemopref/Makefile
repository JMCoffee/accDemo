ifdef SIMULATOR
	TARGET = simulator:clang:11.2:8.0
	ARCHS = x86_64
else
	TARGET = iphone:clang:11.2:7.0
	ARCHS= armv7 arm64 arm64e
endif

BUNDLE_NAME = accDemo

accDemo_FILES = $(wildcard *.m) LowiOSVersionCompatibility.x
accDemo_INSTALL_PATH = /Library/PreferenceBundles
accDemo_FRAMEWORKS = UIKit
accDemo_PRIVATE_FRAMEWORKS = Preferences
accDemo_CFLAGS = -fobjc-arc -Wno-error=unused-variable -Wno-error=unused-function -include Prefix.pch
accDemo_LIBRARIES = applist

include $(THEOS)/makefiles/common.mk
include $(THEOS_MAKE_PATH)/bundle.mk

internal-stage::
	$(ECHO_NOTHING)mkdir -p $(THEOS_STAGING_DIR)/Library/PreferenceLoader/Preferences$(ECHO_END)
	$(ECHO_NOTHING)cp entry.plist $(THEOS_STAGING_DIR)/Library/PreferenceLoader/Preferences/accDemo.plist$(ECHO_END)
