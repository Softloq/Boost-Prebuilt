cmake_minimum_required(VERSION 3.10)

project(Boost-Prerequisite)

# Download Boost
if(NOT EXISTS "${CMAKE_BINARY_DIR}/Downloads/boost-${BOOST_VERSION}.zip")
    file(DOWNLOAD "https://github.com/boostorg/boost/releases/download/boost-${BOOST_VERSION}/boost-${BOOST_VERSION}-b2-nodocs.zip" "${CMAKE_BINARY_DIR}/Downloads/boost-${BOOST_VERSION}.zip" SHOW_PROGRESS)
endif()
if(NOT EXISTS "${CMAKE_BINARY_DIR}/Downloads/boost-${BOOST_VERSION}")
    file(ARCHIVE_EXTRACT INPUT "${CMAKE_BINARY_DIR}/Downloads/boost-${BOOST_VERSION}.zip" DESTINATION "${CMAKE_BINARY_DIR}/Downloads")
endif()
