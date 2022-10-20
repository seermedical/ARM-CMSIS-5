cmake_minimum_required (VERSION 3.14)

#Set target CPU
set(ARM_CPU "cortex-m4")

# Specify prefix
set(PREFIX arm-none-eabi-)

# Specify toolchain
set(CMAKE_TOOLCHAIN_FILE gcc.cmake)

# Define the project
project (CMSISDSPLibs VERSION 1.0)

# Set ROOT of CMSIS library
set(ROOT ${CMAKE_CURRENT_SOURCE_DIR}/../..)

#Enable optimisations
set(OPTIMIZED ON)

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
