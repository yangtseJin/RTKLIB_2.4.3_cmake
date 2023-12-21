cmake_minimum_required(VERSION 3.1)
project($LIB_NAME$)

add_definitions(-DTRACE)#enable trace in rtklib

# 添加头文件
include_directories(${HEAD_PATH})

# 搜索指定目录下源文件,两种方法选一个即可
# 将源文件存储到变量 RTKLIB_SRC 中
# 法1
file(GLOB_RECURSE RTKLIB_SRC ${SRC_PATH}/*.c)
# 法2
# aux_source_directory(${SRC_PATH} RTKLIB_SRC)

# 编译成静态库
add_library(${LIB_NAME} STATIC ${RTKLIB_SRC})


# 安装编译好的rtklib库，如果需要安装，请解开这里的两个install的注释
#install(TARGETS rtklib
#        LIBRARY DESTINATION lib
#        ARCHIVE DESTINATION lib)
#
#install(FILES rtklib.h DESTINATION include)