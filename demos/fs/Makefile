# A Makefile for fs

include $(LITEOSTOPDIR)/config.mk
MODULE_NAME := fs_demo

LOCAL_SRCS :=
LOCAL_SRCS_y :=
C_DEFS :=

LOCAL_SRCS_$(LOSCFG_DEMOS_FS_FAT) += fs_common.c fatfs_demo.c
LOCAL_SRCS_$(LOSCFG_DEMOS_FS_SPIF) += fs_common.c spiffs_demo.c

ifeq ($(LOSCFG_DEMOS_FS), y)
LOCAL_INCLUDE += -I $(LITEOSTOPDIR)/include
endif

ifeq ($(LOSCFG_DEMOS_FS_FAT), y)
LOCAL_INCLUDE += -I $(LITEOSTOPDIR)/demos/fs
C_DEFS += -D FS_FATFS
endif

ifeq ($(LOSCFG_DEMOS_FS_SPIF), y)
LOCAL_INCLUDE += -I $(LITEOSTOPDIR)/demos/fs
C_DEFS += -D FS_SPIFFS
endif
BOARD_DEF += $(C_DEFS)

ifeq ($(LOSCFG_PLATFORM_STM32F429IGTX), y)
LOCAL_INCLUDE += \
            -I $(LITEOSTOPDIR)/targets/Cloud_STM32F429IGTx_FIRE/Inc \
            -I $(LITEOSTOPDIR)/targets/Cloud_STM32F429IGTx_FIRE/Hardware/Inc
endif

ifeq ($(LOSCFG_PLATFORM_STM32L431_BearPi), y)
LOCAL_INCLUDE += \
            -I $(LITEOSTOPDIR)/targets/STM32L431_BearPi/Inc \
            -I $(LITEOSTOPDIR)/targets/STM32L431_BearPi/Hardware/Inc
endif

LOCAL_SRCS   = $(LOCAL_SRCS_y)
LOCAL_FLAGS :=  $(BOARD_DEF) $(LOCAL_INCLUDE)

include $(MODULE)
