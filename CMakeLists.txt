cmake_minimum_required(VERSION 3.18)
project(ExampleProgram)

set(CMAKE_CXX_STANDARD 11)

add_executable(TcpClient TcpClient.cc)
add_executable(TcpServer TcpServer.cc)

# Add -lpthread
target_link_libraries(TcpClient pthread)
target_link_libraries(TcpServer pthread)

# Add -I../async-sockets
target_include_directories(TcpClient PUBLIC TcpClient.h)
target_include_directories(TcpServer PUBLIC TcpServer.h)
