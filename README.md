More details about the setup can be found here:
https://adrianalin.gitlab.io/popsblog.me/posts/build-linux-for-stm32f769i-disco-using-buildroot/

## How to patch m4 to build with glibc 2.34 or higher
1. build
```bash
make bootstrap
make build
```

2. patch c-stack.c & c-stack.h in built buildroot directory
```bash
cd buildroot/output/build/host-m4-1.4.18/lib
patch -b < STM32F769I-disco_Buildroot/m4_patch/0003-c-stack-stop-using-SIGSTKSZ.patch
```

3. build again
```bash
make build
```
## How to patch fakeroot to build with glibc 2.34 or higher
1. build
```bash
make bootstrap
make build
```

2. patch buildroot directory
```bash
cd buildroot/output/build/host-fakeroot-1.20.2
patch -b < STM32F769I-disco_Buildroot/fakeroot_patch/no_STAT_VER.patch
```

3. build again
```bash
make build
```
