

build_library_in_subdir(simlib
  NAME grass_sim
  DEPENDS grass_datetime grass_raster grass_vector
  HEADERS "waterglobs.h" "simlib.h"   )

#add_subdirectory(simlib)
# build_module(NAME simlib
#   DEPENDS grass_datetime grass_raster grass_vector
#   HEADERS "waterglobs.h;simlib.h"   )

build_program_in_subdir(
  r.sim.water
  DEPENDS grass_gis grass_gmath grass_sim
  INCLUDES "../simlib")

build_program_in_subdir(
  r.sim.sediment
  DEPENDS grass_gis grass_gmath grass_sim
  INCLUDES "../simlib")
