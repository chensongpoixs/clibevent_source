project(Server)
CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
MESSAGE(STATUS "#########################")
SET(CMAKE_BUILD_TYPE Release)
#ADD_DEFINITIONS(-std=c++11 -g -Wall )
#
#SET(EXTRA_INC_DIR /home/ext)
#
INCLUDE_DIRECTORIES(
					${PROJECT_SOURCE_DIR}/include
					${PROJECT_SOURCE_DIR}/WIN32-Code
					${PROJECT_SOURCE_DIR}/compat
#					/usr/local/include
#					${EXTRA_INC_DIR}/include
#					${PROJECT_SOURCE_DIR}/clib
#					${PROJECT_SOURCE_DIR}/common
#					${PROJECT_SOURCE_DIR}/common/cmsg
#					${PROJECT_SOURCE_DIR}/common/cmessage
#					#${PROJECT_SOURCE_DIR}/Robot
					)


				
				
SET(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/linux/lib )
SET(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/linux)

LINK_DIRECTORIES(
#				/usr/local/lib
#				/usr/local/lib64
#				/usr/lib/x86_64-linux-gnu
				${PROJECT_SOURCE_DIR}/linux/lib
				)
file(GLOB ALL_CXX_SRCS
		./*.cpp  ./*.cc
		./*.c
		)

add_executable(${PROJECT_NAME} ${ALL_CXX_SRCS})
#add_dependencies(${PROJECT_NAME} common)
#add_dependencies(${PROJECT_NAME} clib)

set(ALL_LIB
#pthread
#		libcommon.a
#		libclib.a
#		libprotobuf-lite.a
#		libthrift.a
#		libmysqlclient.so
#		libjsoncpp.a
#		libboost_locale.a
#		libboost_regex.a
#		libboost_system.a
#		libboost_filesystem.a

		)


target_link_libraries(${PROJECT_NAME} ${ALL_LIB})
				
#add_subdirectory(clib)
#add_subdirectory(common)
#add_subdirectory(gateway)
#add_subdirectory(Robot)