  
build_program_in_subdir(g.access DEPENDS grass_gis )
build_program_in_subdir(g.copy DEPENDS grass_manage )
build_program_in_subdir(g.dirseps DEPENDS grass_gis )
build_program_in_subdir(g.filename DEPENDS grass_gis )
build_program_in_subdir(g.findetc DEPENDS grass_gis )
build_program_in_subdir(g.findfile DEPENDS grass_manage )
build_program_in_subdir(g.gisenv DEPENDS grass_gis )
build_program_in_subdir(g.list DEPENDS grass_manage)
build_program_in_subdir(g.mapset DEPENDS grass_gis )
build_program_in_subdir(g.mapsets DEPENDS grass_gis )
build_program_in_subdir(g.message DEPENDS grass_gis )
build_program_in_subdir(g.mkfontcap DEPENDS grass_gis FREETYPE )
build_program_in_subdir(g.parser DEPENDS grass_gis FREETYPE )
build_program_in_subdir(g.pnmcomp DEPENDS grass_gis )
build_program_in_subdir(g.ppmtopng DEPENDS grass_gis LIBPNG)
build_program_in_subdir(g.proj DEPENDS grass_gis grass_gproj GDAL )
build_program_in_subdir(g.region DEPENDS grass_gis grass_gproj
  grass_vector grass_raster3d grass_gmath)

build_program_in_subdir(g.remove DEPENDS grass_manage grass_raster )
build_program_in_subdir(g.rename DEPENDS grass_manage grass_raster )
build_program_in_subdir(g.tempfile DEPENDS grass_gis )


#TODO
set(GRASS_VERSION_UPDATE_PKG "0.2")
set(BUILD_ARCH "x86_64")

build_program_in_subdir(g.version DEPENDS grass_gis GEOS GDAL
#  DEFS "-DGRASS_VERSION_NUMBER=1;-DGRASS_VERSION_DATE=${GRASS_VERSION_DATE};-DGRASS_VERSION_SVN=45454;-DGRASS_VERSION_UPDATE_PKG=0.2;-DARCH='x86_64'"
DEFS "-DGRASS_VERSION_NUMBER=\"${GRASS_VERSION_NUMBER}\""
     "-DGRASS_VERSION_SVN=\"${GRASS_VERSION_SVN}\""
     "-DGRASS_VERSION_UPDATE_PKG=${GRASS_VERSION_UPDATE_PKG}"
     "-DARCH=\"${BUILD_ARCH}\""
  )

if(WITH_CAIRO)
  build_program_in_subdir(g.cairocomp DEPENDS grass_gis grass_cairodriver)
endif()

# g.cairocomp
# g.gui
add_subdirectory(manage/lister)



