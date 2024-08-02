# G3748
Supermico patch script to do git patch/apply all open PRs required to build SONiC image for SSE-G3748 switch.

## SONIC-202211-patch
Patch and script files for building SONiC 202211 version.

    git clone https://github.com/sonic-net/sonic-buildimage.git -b 202211
    git clone https://github.com/supermicro/G3748.git

    cd sonic-buildimage
    git checkout 86c1bf5c155eb0a88c82a2adc6f4398b2794232f

    make init
    
    bash ../G3748/SONiC-202211-patch/sonic_202211_apply_patch_bullseye.sh
    bash ../G3748/SONiC-202211-patch/sonic_202211_apply_smc_patch_bullseye.sh
    
    NOBUSTER=1 NOSTRETCH=1 make configure PLATFORM=marvell-arm64 PLATFORM_ARCH=arm64
    
    NOBUSTER=1 NOSTRETCH=1 SONIC_BUILD_JOBS=4 make target/sonic-marvell-arm64.bin
