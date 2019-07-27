dtb-$(CONFIG_SEC_STARQLTE_PROJECT) += sdm845-sec-starqlte-r14.dtb

dtb-$(CONFIG_SEC_STAR2QLTE_PROJECT) += sdm845-sec-star2qlte-r14.dtb

dtb-$(CONFIG_SEC_CROWNQLTE_PROJECT) += sdm845-sec-crownqlte-r10.dtb

dtb-$(CONFIG_SEC_LYKANLTE_PROJECT) += sdm845-sec-lykanlte-r05.dtb

ifeq ($(filter y,$(CONFIG_MACH_STARQLTE_CHNZC) $(CONFIG_MACH_STARQLTE_CHNZM) $(CONFIG_MACH_STARQLTE_CHN_LDU)),y)
dtb-y = sdm845-sec-starqlte-chn-r14_v2.1.dtb
endif

ifeq ($(filter y,$(CONFIG_MACH_STAR2QLTE_CHNZC) $(CONFIG_MACH_STAR2QLTE_CHN_LDU)),y)
dtb-y = sdm845-sec-star2qlte-chn-r14_v2.1.dtb
endif

ifeq ($(filter y,$(CONFIG_MACH_STARQLTE_CHNHK)),y)
dtb-y = sdm845-sec-starqlte-chnhk-r14_v2.1.dtb
endif

ifeq ($(filter y,$(CONFIG_MACH_STAR2QLTE_CHNHK)),y)
dtb-y = sdm845-sec-star2qlte-chnhk-r14_v2.1.dtb
endif

ifeq ($(filter y,$(CONFIG_MACH_STARQLTE_DCM) $(CONFIG_MACH_STARQLTE_KDI)),y)
dtb-y = sdm845-sec-starqlte-jpn-r14.dtb
endif

ifeq ($(filter y,$(CONFIG_MACH_STAR2QLTE_DCM) $(CONFIG_MACH_STAR2QLTE_KDI)),y)
dtb-y = sdm845-sec-star2qlte-jpn-r14.dtb
endif

ifeq ($(filter y,$(CONFIG_MACH_CROWNQLTE_CHNZC) $(CONFIG_MACH_CROWNQLTE_CHNZM) $(CONFIG_MACH_CROWNQLTE_CHN_LDU)),y)
dtb-y =	sdm845-sec-crownqlte-chn-r10.dtb
endif

ifeq ($(filter y,$(CONFIG_MACH_CROWNQLTE_CHNHK)),y)
dtb-y =	sdm845-sec-crownqlte-chnhk-r10.dtb
endif

ifeq ($(filter y,$(CONFIG_MACH_CROWNQLTE_DCM) $(CONFIG_MACH_CROWNQLTE_KDI)),y)
dtb-y = sdm845-sec-crownqlte-jpn-r03.dtb	
endif

ifeq ($(filter y,$(CONFIG_MACH_LYKANLTE_CHNZC) $(CONFIG_MACH_LYKANLTE_CHNLDU)),y)
dtb-y =	sdm845-sec-lykanlte-chn-r05.dtb
endif

ifeq ($(CONFIG_ARM64),y)
always          := $(dtb-y)
subdir-y        := $(dts-dirs)
else
targets += dtbs
targets += $(addprefix ../, $(dtb-y))

$(obj)/../%.dtb: $(src)/%.dts FORCE
        $(call if_changed_dep,dtc)

dtbs: $(addprefix $(obj)/../,$(dtb-y))
endif
clean-files := *.dtb *.reverse.dts

