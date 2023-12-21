cmake_minimum_required(VERSION 3.1) #最低cmake版本要求
project(consapp) #定义项目名称

# 包含库文件路径
link_directories(${LIB_PATH})

# 添加头文件
include_directories(
        ${HEAD_PATH}
        # 如果已经将rtklib安装到系统路径中，指定rtklib库的路径
        # usr/local/include/rtklib
)

# 将所需要的库放进一个变量中
set(EXE_LIB ${LIB_NAME} m pthread)

# 链接库时有两种方法
# 法1：link_libraries链接静态库，后面的可执行文件均可使用
link_libraries(${EXE_LIB})

# 添加可执行文件
add_executable(convbin convbin/convbin.c )
# 法2：target_link_libraries为每个可执行文件单独链接，本质上还是链接的静态库，但是方便修改需要的库
#target_link_libraries(convbin ${LIB_NAME} m)

add_executable(pos2kml pos2kml/pos2kml.c)
#target_link_libraries(pos2kml ${LIB_NAME} m)

add_executable(rnx2rtkp rnx2rtkp/rnx2rtkp.c)
#target_link_libraries(rnx2rtkp ${LIB_NAME} m)

include_directories(rtkrcv)
add_executable(rtkrcv rtkrcv/rtkrcv.c rtkrcv/vt.c)
#target_link_libraries(rtkrcv ${LIB_NAME} m pthread)

add_executable(str2str str2str/str2str.c)
#target_link_libraries(str2str ${LIB_NAME} m pthread)

