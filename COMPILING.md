### win32
```bash
cmake \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_C_COMPILER=/usr/local/Cellar/mingw-w64/6.0.0/bin/i686-w64-mingw32-gcc \
    -DCMAKE_CXX_COMPILER=/usr/local/Cellar/mingw-w64/6.0.0/bin/i686-w64-mingw32-g++ \
    -DBUILD_SHARED_LIBS=OFF \
    -DENABLE_STATIC_RUNTIME=ON \
    -DCMAKE_SYSTEM_NAME=Windows \
    -DCMAKE_SYSTEM_PROCESSOR=x86 \
    -DCMAKE_SYSTEM_VERSION=8.1 \
    -DCMAKE_C_COMPILER_TARGET=x86-pc-win32 \
    -DCMAKE_CXX_COMPILER_TARGET=x86-pc-win32 \
    -DZLIB_INCLUDE_DIR=/usr/local/opt/zlib/include \
    -DZLIB_LIBRARY=/usr/local/opt/zlib/lib \
    -G "CodeBlocks - Unix Makefiles" \
    .
    
make
```

### win64

```bash
cmake \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_C_COMPILER=/usr/local/Cellar/mingw-w64/6.0.0/bin/x86_64-w64-mingw32-gcc \
    -DCMAKE_CXX_COMPILER=/usr/local/Cellar/mingw-w64/6.0.0/bin/x86_64-w64-mingw32-g++ \
    -DBUILD_SHARED_LIBS=OFF \
    -DENABLE_STATIC_RUNTIME=ON \
    -DCMAKE_SYSTEM_NAME=Windows \
    -DCMAKE_SYSTEM_PROCESSOR=x86_64 \
    -DCMAKE_SYSTEM_VERSION=8.1 \
    -DCMAKE_C_COMPILER_TARGET=x64-pc-win32 \
    -DCMAKE_CXX_COMPILER_TARGET=x64-pc-win32 \
    -DZLIB_INCLUDE_DIR=/usr/local/opt/zlib/include \
    -DZLIB_LIBRARY=/usr/local/opt/zlib/lib \
    -G "CodeBlocks - Unix Makefiles" \
    .
    
make
```

### arm

```bash
export ANDROID_SDK=/Users/sam/Library/Android/sdk
cmake \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_C_COMPILER=${ANDROID_SDK}/ndk-bundle/build/tools/arm_api-23/bin/arm-linux-androideabi-clang \
    -DCMAKE_CXX_COMPILER=${ANDROID_SDK}/ndk-bundle/build/tools/arm_api-23/bin/arm-linux-androideabi-clang++ \
    "-DCMAKE_CXX_FLAGS=-fPIE -fPIC -lstdc++" \
    -DCMAKE_AR=${ANDROID_SDK}/ndk-bundle/build/tools/arm_api-23/bin/arm-linux-androideabi-ar \
    -DCMAKE_RANLIB=${ANDROID_SDK}/ndk-bundle/build/tools/arm_api-23/bin/arm-linux-androideabi-ranlib \
    -DCMAKE_OSX_SYSROOT=/ \
    -DCMAKE_OSX_DEPLOYMENT_TARGET= \
    -G "CodeBlocks - Unix Makefiles" \
    .

make
```

### arm64

```bash
export ANDROID_SDK=/Users/sam/Library/Android/sdk
cmake \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_C_COMPILER=${ANDROID_SDK}/ndk-bundle/build/tools/arm64_api-23/bin/aarch64-linux-androideabi-clang \
    -DCMAKE_CXX_COMPILER=${ANDROID_SDK}/ndk-bundle/build/tools/arm64_api-23/bin/aarch64-linux-androideabi-clang++ \
    "-DCMAKE_CXX_FLAGS=-fPIE -fPIC -lstdc++" \
    -DCMAKE_AR=${ANDROID_SDK}/ndk-bundle/build/tools/arm64_api-23/bin/aarch64-linux-androideabi-ar \
    -DCMAKE_RANLIB=${ANDROID_SDK}/ndk-bundle/build/tools/arm64_api-23/bin/aarch64-linux-androideabi-ranlib \
    -DCMAKE_OSX_SYSROOT=/ \
    -DCMAKE_OSX_DEPLOYMENT_TARGET= \
    -G "CodeBlocks - Unix Makefiles" \
    .

make
```

### darwin

```bash
cmake -DCMAKE_BUILD_TYPE=Release -G "CodeBlocks - Unix Makefiles" .
make
```