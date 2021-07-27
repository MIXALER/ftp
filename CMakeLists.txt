cmake_minimum_required(VERSION 3.17)

project(ftp)

set(CMAKE_CXX_STANDARD 11)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin)


add_executable(ftp_epoll_server server/server.c server/ftp_server.h server/handle.c server/ftp_server_func.c)

add_executable(ftp_epoll_client client/client.c client/ftp_client_func.c client/ftp_client.h)

FIND_PACKAGE(Threads)
TARGET_LINK_LIBRARIES(ftp_epoll_server ${CMAKE_THREAD_LIBS_INIT})
TARGET_LINK_LIBRARIES(ftp_epoll_client ${CMAKE_THREAD_LIBS_INIT})
