set(srcs "dport_panic_highint_hdl.S")
add_prefix(srcs "${CMAKE_CURRENT_LIST_DIR}/" ${srcs})

#ld_include_panic_highint_hdl is added as an undefined symbol because otherwise the
#linker will ignore panic_highint_hdl.S as it has no other files depending on any
#symbols in it.
set_property(TARGET ${COMPONENT_LIB} APPEND PROPERTY INTERFACE_LINK_LIBRARIES "-u ld_include_panic_highint_hdl")
