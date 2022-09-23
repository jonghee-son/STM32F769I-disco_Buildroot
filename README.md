More details about the setup can be found here:
https://adrianalin.gitlab.io/popsblog.me/posts/build-linux-for-stm32f769i-disco-using-buildroot/

## How to patch m4 to build with glibc 2.34 or higher
1. build bootstrap
```bash
make bootstrap
```

2. patch c-stack.c & c-stack.h in built buildroot directory
```bash
cd buildroot/output/build/host-m4-1.4.18/lib
patch -b < 0003-c-stack-stop-using-SIGSTKSZ.patch
```
