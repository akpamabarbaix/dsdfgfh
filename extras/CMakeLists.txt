function(rwkv_add_extra source)
	get_filename_component(EXTRA_TARGET ${source} NAME_WE)
	add_executable(rwkv_${EXTRA_TARGET} ${source})
	target_link_libraries(rwkv_${EXTRA_TARGET} PRIVATE ggml rwkv)
endfunction()

file(GLOB extras *.c)
foreach (extra ${extras})
	rwkv_add_extra(${extra})
endforeach()