set( LIB_NAME       "rapidDds" )
set( DIR_NAME       "${LIB_NAME}" )
set( EXPORT_SUFFIX  "${LIB_NAME}" )

file( GLOB ALL_IDL_FILENAMES "${CMAKE_CURRENT_SOURCE_DIR}/*.idl" )

set( EXTRA_RTIDDS_IDL_ARGS -I ${CMAKE_CURRENT_SOURCE_DIR}/..)

rtidds_wrap_idl( ${ALL_IDL_FILENAMES} )

include_directories( ${RTIDDS_INCLUDE_DIR} )
link_libraries( ${RTIDDS_LIBRARIES} )

add_srcdir_definitions(${RTIDDS_EXPORT} ${RTIDDS_DEFINES})

add_library( ${LIB_NAME} SHARED
  ${RTIDDS_IDL_GENERATED}
)

install_library( ${LIB_NAME} )
install_files  ( /include/${DIR_NAME}              FILES ${RTIDDS_IDL_GENERATED_HEADERS})
install_files  ( /idl/${DIR_NAME}                  FILES ${ALL_IDL_FILENAMES} )
install_files  ( /etc/rtiRoutingService/           FILES ${RTIDDS_IDL_GENERATED_XMLS} )
install_files  ( /etc/rtiRoutingServiceMcc/        FILES ${RTIDDS_IDL_GENERATED_XMLS} )
install_files  ( /etc/rtiRoutingServiceGramps/     FILES ${RTIDDS_IDL_GENERATED_XMLS} )
install_files  ( /etc/rtiRoutingServiceRoverscape/ FILES ${RTIDDS_IDL_GENERATED_XMLS} )
install_files  ( /etc/rtiRoutingServiceMvp/        FILES ${RTIDDS_IDL_GENERATED_XMLS} )
install_files  ( /etc/rtiRoutingServiceSnrf/       FILES ${RTIDDS_IDL_GENERATED_XMLS} )
install_files  ( /etc/rtiRecordingService/types/   FILES ${RTIDDS_IDL_GENERATED_XMLS} )
