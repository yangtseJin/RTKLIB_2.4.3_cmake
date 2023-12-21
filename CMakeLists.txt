cmake_minimum_required(VERSION 3.1) #最低cmake版本要求
project(rktlib_manager) #定义项目名称

# 设置C++的编译标准
set(CMAKE_CXX_STANDARD 11)
# 设置优化选项、显示所有警告
set(CMAKE_CXX_FLAGS_RELEASE "-O3 -Wall -g")

# 指定编译模式
IF (NOT CMAKE_BUILD_TYPE)
    SET(CMAKE_BUILD_TYPE Release)
ENDIF ()
MESSAGE("Build type: " ${CMAKE_BUILD_TYPE})

# 预定义头文件路径
set(HEAD_PATH ${PROJECT_SOURCE_DIR}/src)
# 预定义源文件路径
set(SRC_PATH ${PROJECT_SOURCE_DIR}/src)
# 预定义库文件路径
set(LIB_PATH ${PROJECT_SOURCE_DIR}/lib_rtk)
# 预定义可执行二进制文件路径
set(EXEC_PATH ${PROJECT_SOURCE_DIR}/bin)

# 设置库文件的输出路径
set(LIBRARY_OUTPUT_PATH ${LIB_PATH})
# 设置二进制可执行文件的输出路径
set(EXECUTABLE_OUTPUT_PATH ${EXEC_PATH})

# 设置编译好的库的名称
set(LIB_NAME rtklib)


# 安装库，新手一般不需要使用
# 指定安装路径
#set(CMAKE_INSTALL_PREFIX "/usr/local")

# 添加子目录
add_subdirectory(src)
add_subdirectory(app/consapp)
