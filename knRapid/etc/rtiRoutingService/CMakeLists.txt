file( GLOB ALL_ROUTING_SERVICE "${CMAKE_CURRENT_SOURCE_DIR}/RTI_ROUTING_SERVICE*" )
file( GLOB ALL_DISCOVERY_PEERS "${CMAKE_CURRENT_SOURCE_DIR}/NDDS_DISCOVERY_PEERS*" )
file( GLOB ALL_UTILITY_SCRIPTS "${CMAKE_CURRENT_SOURCE_DIR}/*.sh" "${CMAKE_CURRENT_SOURCE_DIR}/*.bat"  )

install_files(/etc/rtiRoutingService FILES ${ALL_ROUTING_SERVICE} )
install_files(/etc/rtiRoutingService FILES ${ALL_DISCOVERY_PEERS} )
install_files(/etc/rtiRoutingService FILES ${ALL_UTILITY_SCRIPTS} )
