cmake_minimum_required (VERSION 3.14)

# Define the project
project (CMSISDSPLibs VERSION 1.0)

# Define the path to CMSIS-DSP
set(DSP ${ROOT}/CMSIS/DSP)

# Add DSP folder to module path
list(APPEND CMAKE_MODULE_PATH ${DSP})

########### 
#
# CMSIS DSP
#

# Load CMSIS-DSP definitions. Libraries will be built in dsp_libs
add_subdirectory(${DSP}/Source dsp_libs)
