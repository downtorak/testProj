cmake_minimum_required(VERSION 2.8)

project(TestProject)
set(VERSION 1.0.5)
set(BASE_PATH ${PROJECT_SOURCE_DIR})
configure_file(${BASE_PATH}/VERSION.in ${BASE_PATH}/VERSION)
configure_file(${BASE_PATH}/Version.h.in ${BASE_PATH}/src/Version.h)

include_directories(${BASE_PATH}/src)
add_executable(test ${BASE_PATH}/src/main.cpp)

install(TARGETS test DESTINATION TestProject)
install(FILES ${BASE_PATH}/VERSION DESTINATION TestProject)

set(CPACK_PACKAGE_NAME test)
set(CPACK_PACKAGE_VERSION ${VERSION})
set(CPACK_PACKAGE_FILE_NAME ${CPACK_PACKAGE_NAME}-${CPACK_PACKAGE_VERSION})
set(CPACK_INCLUDE_TOPLEVEL_DIRECTORY FALSE)
set(CPACK_GENERATOR TGZ)
include(CPack)
