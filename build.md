
#### windows

    直接使用build/vs2017下项目直接运行编译即可

#### macosx
    1. arm64
        cmake .. \
        -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=/Users/mac/Downloads/github/uavs3d/install/macosx/arm64/release \
        -DCMAKE_OSX_ARCHITECTURES=arm64 \
        -DCMAKE_OSX_DEPLOYMENT_TARGET=10.15 \
        -DBUILD_SHARED_LIBS=OFF \
        -DCOMPILE_10BIT=ON

        make -j$(sysctl -n hw.ncpu)
        make install

    2. x86_64
        cmake .. \
        -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=/Users/mac/work/player-deps/install/macosx/uavs3d/x86_64/release \
        -DCMAKE_SYSTEM_NAME=Darwin \
        -DCMAKE_SYSTEM_PROCESSOR=x86_64 \
        -DCMAKE_OSX_ARCHITECTURES=x86_64 \
        -DCMAKE_OSX_DEPLOYMENT_TARGET=10.15 \
        -DBUILD_SHARED_LIBS=OFF \
        -DCOMPILE_10BIT=ON

        make -j$(sysctl -n hw.ncpu)
        make install

#### ios

    cmake .. \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/Users/mac/work/player-deps/install/iphoneos/uavs3d/arm64/release \
    -DCMAKE_SYSTEM_NAME=iOS \
    -DCMAKE_SYSTEM_PROCESSOR=arm64 \
    -DCMAKE_OSX_ARCHITECTURES=arm64 \
    -DCMAKE_OSX_DEPLOYMENT_TARGET=13.0 \
    -DBUILD_SHARED_LIBS=OFF \
    -DCOMPILE_10BIT=ON

    cmake --build . --target uavs3d -j $(sysctl -n hw.ncpu)
    cmake --install .

#### appletvos

    cmake .. \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/Users/mac/work/player-deps/install/appletvos/uavs3d/arm64/release \
    -DCMAKE_SYSTEM_NAME=tvOS \
    -DCMAKE_SYSTEM_PROCESSOR=arm64 \
    -DCMAKE_OSX_ARCHITECTURES=arm64 \
    -DCMAKE_OSX_DEPLOYMENT_TARGET=17.0 \
    -DBUILD_SHARED_LIBS=OFF \
    -DCOMPILE_10BIT=ON

    make -j$(sysctl -n hw.ncpu) uavs3d
    cmake --install .

#### android

    1. arm64-v8a
        NDK=/Users/mac/Library/Android/sdk/ndk/21.1.6352462

        cmake .. \
        -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=/Users/mac/work/player-deps/install/android/uavs3d/arm64-v8a/release \
        -DCMAKE_TOOLCHAIN_FILE=$NDK/build/cmake/android.toolchain.cmake \
        -DANDROID_ABI=arm64-v8a \
        -DANDROID_PLATFORM=android-21 \
        -DBUILD_SHARED_LIBS=OFF \
        -DCOMPILE_10BIT=ON

        make -j$(sysctl -n hw.ncpu) uavs3d
        cmake --install .
    
    2. armeabi-v7a
        NDK=/Users/mac/Library/Android/sdk/ndk/21.1.6352462

        cmake .. \
        -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=/Users/mac/work/player-deps/install/android/uavs3d/armeabi-v7a/release \
        -DCMAKE_TOOLCHAIN_FILE=$NDK/build/cmake/android.toolchain.cmake \
        -DANDROID_ABI=armeabi-v7a \
        -DANDROID_ARM_NEON=ON \
        -DANDROID_PLATFORM=android-17 \
        -DBUILD_SHARED_LIBS=OFF \
        -DCOMPILE_10BIT=ON

        make -j$(sysctl -n hw.ncpu) uavs3d
        cmake --install .