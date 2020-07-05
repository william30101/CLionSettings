cmake_minimum_required(VERSION 3.16)
project(android_kernel)
add_definitions(-DANDROID)

set(PROJECT_DIR "/home/william/Documents/android-kernel")

set(CMAKE_C_COMPILER ${PROJECT_DIR}/prebuilts/gcc/linux-x86/arm/arm-linux-androideabi-4.9/bin/arm-linux-androideabi-gcc)
set(CMAKE_CXX_COMPILER ${PROJECT_DIR}/prebuilts/gcc/linux-x86/arm/arm-linux-androideabi-4.9/bin/arm-linux-androideabi-gcc)
add_executable("android_kernel" cmake-build-debug/main.c)

include_directories(
        "${PROJECT_DIR}/private/msm-google/include"
        "${PROJECT_DIR}/private/msm-google/arch/arm/include"
        "${PROJECT_DIR}/private/msm-google/arch/arm64/include"
#        "${PROJECT_DIR}/out/target/product/msm8952_64/obj/KERNEL_OBJ/usr/include"
        "${PROJECT_DIR}/private/msm-google/mm"
)
