cmake_minimum_required(VERSION 3.0.0)
project(client)

set(ZEROMQ_PATH "C:/Users/Administrator/Desktop/win64CppZeromq/2.ZeroMQ")

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS}  -std=c++17")

set(SOURCE client.cpp)

include_directories(
    . 
    ${ZEROMQ_PATH}/include
)

link_directories(
    ${ZEROMQ_PATH}/lib
)

add_executable(
    ${PROJECT_NAME} 
    ${SOURCE}
)

TARGET_LINK_LIBRARIES(
    ${PROJECT_NAME} 
    ${ZEROMQ_PATH}/lib/libzmq.a
    ${ZEROMQ_PATH}/lib/libzmq.dll.a
)