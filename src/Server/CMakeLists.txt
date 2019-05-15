cmake_minimum_required(VERSION 3.7)
project(server)

set(CMAKE_CXX_STANDARD 11)

set(SOURCE_FILES main.cpp chat_message.h)
add_executable(server ${SOURCE_FILES})

find_package(Boost COMPONENTS system filesystem REQUIRED)
IF (Boost_FOUND)
    include_directories(${Boost_INCLUDE_DIR})
    target_link_libraries(server
            ${Boost_FILESYSTEM_LIBRARY}
            ${Boost_SYSTEM_LIBRARY}
            )
endif()