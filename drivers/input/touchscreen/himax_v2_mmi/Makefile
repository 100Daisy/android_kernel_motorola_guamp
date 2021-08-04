ccflags-y += -I$(src)/support_ic

ifneq ($(filter m y,$(CONFIG_TOUCHSCREEN_HIMAX_IC_HX83112F)),)
	ccflags-y += -D__HIMAX_HX83112_MOD__
	ccflags-y += -DHX_FIX_TOUCH_INFO
	ccflags-y += -DHX_112F_SET
# Fixed warning: variable length array used [-Wvla]
	ccflags-y += -DFIX_WVLA
	ccflags-y += -I$(src)/support_ic/himax_v2_mmi_hx83112f
endif

ifneq ($(filter m y,$(CONFIG_TOUCHSCREEN_HIMAX_IC_HX83112)),)
	ccflags-y += -D__HIMAX_HX83112_MOD__
	ccflags-y += -I$(src)/support_ic/himax_v2_mmi_hx83112
endif

ifneq ($(filter m y,$(CONFIG_TOUCHSCREEN_HIMAX_IC_HX83102)),)
	ccflags-y += -D__HIMAX_HX83102_MOD__
	ccflags-y += -I$(src)/support_ic/himax_v2_mmi_hx83102
endif

ifneq ($(filter m y,$(CONFIG_TOUCHSCREEN_HIMAX_IC_HX83102D)),)
	ccflags-y += -D__HIMAX_HX83102D_MOD__
	ccflags-y += -DHX_CODE_OVERLAY
	ccflags-y += -I$(src)/support_ic/himax_v2_mmi_hx83102d
endif

ifneq ($(filter m y,$(CONFIG_TOUCHSCREEN_HIMAX_ENABLE_PALM)),)
	ccflags-y += -DHIMAX_PALM_SENSOR_EN
endif

ifneq ($(filter m y,$(CONFIG_TOUCHSCREEN_HIMAX_ENABLE_DOUBLE_TAP)),)
	ccflags-y += -DHIMAX_V2_SENSOR_EN
endif

ifneq ($(filter m y,$(CONFIG_TOUCHSCREEN_HIMAX_ENABLE_MULTI_BIN)),)
	ccflags-y += -DHIMAX_V2_MULTI_BIN
endif

ifneq ($(filter m y,$(CONFIG_TOUCHSCREEN_HIMAX_PANEL_NOTIFICATIONS)),)
	ccflags-y += -DHIMAX_CONFIG_PANEL_NOTIFICATIONS
endif

ifneq ($(filter m y,$(CONFIG_TOUCHSCREEN_HIMAX_SPI)),)
	himax_v2_mmi-y += himax_platform_QCT_SPI.o
	ccflags-y += -D__HIMAX_PLATFORM_SPI__ \
			-DHX_ZERO_FLASH
endif

himax_v2_mmi-y += himax_common.o
himax_v2_mmi-$(CONFIG_TOUCHSCREEN_HIMAX_DEBUG) += himax_debug.o
himax_v2_mmi-$(CONFIG_TOUCHSCREEN_HIMAX_INCELL) += himax_ic_incell_core.o
himax_v2_mmi-$(CONFIG_TOUCHSCREEN_HIMAX_INSPECT) += himax_inspection.o

obj-$(CONFIG_TOUCHSCREEN_HIMAX_SPI) += himax_v2_mmi.o

himax_v2_mmi_hx83112f-y += support_ic/himax_v2_mmi_hx83112f/himax_ic_HX83112f.o
obj-$(CONFIG_TOUCHSCREEN_HIMAX_IC_HX83112F) += himax_v2_mmi_hx83112f.o

himax_v2_mmi_hx83112-y += support_ic/himax_v2_mmi_hx83112/himax_ic_HX83112.o
obj-$(CONFIG_TOUCHSCREEN_HIMAX_IC_HX83112) += himax_v2_mmi_hx83112.o

himax_v2_mmi_hx83102-y += support_ic/himax_v2_mmi_hx83102/himax_ic_HX83102.o
obj-$(CONFIG_TOUCHSCREEN_HIMAX_IC_HX83102) += himax_v2_mmi_hx83102.o

himax_v2_mmi_hx83102d-y += support_ic/himax_v2_mmi_hx83102d/himax_ic_HX83102d.o
obj-$(CONFIG_TOUCHSCREEN_HIMAX_IC_HX83102D) += himax_v2_mmi_hx83102d.o
