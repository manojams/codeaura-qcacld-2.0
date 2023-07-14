qcacld-2.0
==========
Build instructions
------------------

**1. Download the source code**
```
$ cd
$ git clone https://github.com/manojams/codeaura-qcacld-2.0.git -b CNSS.LEA.NRT_3.0
$ cd qcacld-2.0/
```

**2. Setup the environment**
```
$ export ARCH=arm
$ export CROSS_COMPILE= <tool chain path>/arm-linux-gnueabihf-
```

**3. Build the module**
* `<kernel_path>` must be replaced with the actual path of kernel source code
```
$ KERNEL_SRC=<kernel_path> CONFIG_CLD_HL_SDIO_CORE=y CONFIG_CLD_HL_SDIO_CORE=y CONFIG_PER_VDEV_TX_DESC_POOL=1 SAP_AUTH_OFFLOAD=1 CONFIG_QCA_LL_TX_FLOW_CT=1 CONFIG_WLAN_FEATURE_FILS=y CONFIG_FEATURE_COEX_PTA_CONFIG_ENABLE=y CONFIG_QCA_SUPPORT_TXRX_DRIVER_TCP_DEL_ACK=y CONFIG_WLAN_WAPI_MODE_11AC_DISABLE=y TARGET_BUILD_VARIANT=user CONFIG_NON_QC_PLATFORM=y CONFIG_QCA_BOARD_DATA_USE_BOARD_ID=1 CONFIG_HDD_WLAN_WAIT_TIME=10000 make -j
```
* In order to build the module with debug messages enabled, add `BUILD_DEBUG_VERSION=1` to the previous command

