PROJECT(isp)

CMAKE_MINIMUM_REQUIRED(VERSION 2.6)
if(COMMAND cmake_policy)
      cmake_policy(SET CMP0003 NEW)
endif(COMMAND cmake_policy)

FIND_PACKAGE( OpenCV REQUIRED )

# Declare the target (an executable)
ADD_EXECUTABLE(
isp fetch_raw.cpp 
isp_pipeline.cpp 
blc.cpp 
raw_hist.cpp 
isp_util.cpp 
raw_denoise.cpp 
sony_dol_hdr.cpp 
add_noise.cpp
plot_demo.cpp
bm3d_image_denoising.cpp
yuv_convert.cpp
)

TARGET_LINK_LIBRARIES(isp ${OpenCV_LIBS})

MESSAGE(STATUS "OpenCV_LIBS: ${OpenCV_LIBS}")
