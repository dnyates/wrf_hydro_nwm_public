cmake_minimum_required (VERSION 2.8)

# build the version static library
add_library(hydro_driver STATIC
	module_HYDRO_drv.F
)

target_link_libraries(hydro_driver PUBLIC hydro_mpp)
target_link_libraries(hydro_driver PUBLIC hydro_data_rec)

if (WRF_HYDRO_NUDGING STREQUAL "1")
	target_link_libraries(hydro_driver PUBLIC hydro_nudging)
endif (WRF_HYDRO_NUDGING STREQUAL "1")
