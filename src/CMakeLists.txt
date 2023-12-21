cmake_minimum_required(VERSION 3.1)
project($LIB_NAME$)

add_definitions(-DTRACE)#enable trace in rtklib

# 添加头文件
include_directories(${HEAD_PATH})

# 编译成静态库
add_library(${LIB_NAME} STATIC ${RTKLIB_SRC})


# 安装编译好的rtklib库，如果需要安装，请解开这里的两个install的注释
#install(TARGETS rtklib
#        LIBRARY DESTINATION lib
#        ARCHIVE DESTINATION lib)
#
#install(FILES rtklib.h DESTINATION include)