# gcc-toolchain-prebuild
Gcc tool chain prebuild set



[TOC]

## Cross-Compiler Binaries

### 1. windows build to arm

​	gcc 4.5.2 tested on win7 to build to armv7l

- [arm-none-linux-gnueabi-2011.03-4.5.2-win-to-arm.zip](https://github.com/xzzh999/gcc-tool-chain-prebuild/releases/download/0.1/arm-none-linux-gnueabi-2011.03-4.5.2-win-to-arm.zip)

### 2. linux build to arm

​	gcc 4.5.2 tested on centos 6.5/7 to build to armv7l

- [arm-none-linux-gnueabi-2011.03-4.5.2-linux-to-arm.zip](https://github.com/xzzh999/gcc-tool-chain-prebuild/releases/download/0.1/arm-none-linux-gnueabi-2011.03-4.5.2-linux-to-arm.zip)

### 3. linaro 

- [toolchain-binaries website](https://releases.linaro.org/components/toolchain/binaries/)

### 4. musl

- [toolchains website](https://win.musl.cc/) 

### 5. Sourcery

- [toolchain-services website](https://www.mentor.com/embedded-software/toolchain-services/)



## MinGW-w64 for Windows Compiler Binaries

​	Reference page: 

​	[[MinGW-w64 - for 32 and 64 bit Windows Download]](https://sourceforge.net/projects/mingw-w64/files/)

​    for win64

​	tested on windows 7 64 to build to windows 64

- [x86_64-8.1.0-release-posix-seh-rt_v6-rev0-mingw64.7z](https://github.com/xzzh999/gcc-tool-chain-prebuild/releases/download/0.1/x86_64-8.1.0-release-posix-seh-rt_v6-rev0-mingw64.7z)
- [x86_64-6.4.0-release-posix-seh-rt_v5-rev0-mingw64.7z](https://github.com/xzzh999/gcc-tool-chain-prebuild/releases/download/0.1/x86_64-6.4.0-release-posix-seh-rt_v5-rev0-mingw64.7z)

​	for  win32

- [i686-8.1.0-release-posix-sjlj-rt_v6-rev0-mingw64.7z](https://github.com/xzzh999/gcc-toolchain-prebuild/releases/download/0.1/i686-8.1.0-release-posix-sjlj-rt_v6-rev0-mingw64.7z)

​	for both win32/win64

- [mingw64-10.2.0-crt-8.0.0-with-ada-32+64.7z](https://github.com/xzzh999/gcc-toolchain-prebuild/releases/download/0.1/mingw64-10.2.0-crt-8.0.0-with-ada-32+64.7z)

## Goland Cross Build Settings

- windows build to armv7l

  `Environment`:

  ```
  CC=arm-none-linux-gnueabi-gcc;CXX=arm-none-linux-gnueabi-c++;CGO_ENABLED=1;GOOS=linux;GOARCH=arm;GOARM=7
  ```

  `Go tool arguments`:

  for static library

  ```
  -buildmode=c-archive -o libXXX.a
  ```

  for dynamic library

  ```
  -buildmode=c-shared -o libXXX.so
  ```

  and let  `Use all custom build tags` selected



- windows build to ubuntu 64 bit, etc.

  ```
  GOOS=linux;GOARCH=amd64
  ```



## Find System Glibc Version

```shell
ls -l /lib/libc.so.*
```

```shell
/lib/libc.so.6
```

```shell
ldd --version
```



## Find Missing Dependency

```
objdump -x | grep NEEDED
```



