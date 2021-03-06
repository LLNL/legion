# Copyright 2018 Stanford University
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#


ifndef LG_RT_DIR
$(error LG_RT_DIR variable is not defined, aborting build)
endif

# Flags for directing the runtime makefile what to include
DEBUG           = 0		# Include debugging symbols
OUTPUT_LEVEL    ?= LEVEL_DEBUG	# Compile time logging level
USE_CUDA        ?= 0		# Include CUDA support (requires CUDA)
USE_GASNET       = 1		# Include GASNet support (requires GASNet)
CONDUIT		 = mpi
USE_HDF         ?= 0		# Include HDF5 support (requires HDF5)
ALT_MAPPERS     ?= 0		# Include alternative mappers (not recommended)
USE_HWLOC	 = 1 

# Put the binary file name here
OUTFILE		?= circuit
# List all the application source files here
GEN_SRC		?= circuit.cc circuit_cpu.cc circuit_init.cc circuit_mapper.cc	# .cc files
ifeq ($(strip $(USE_CUDA)),1)
GEN_GPU_SRC	?= circuit_gpu.cu				# .cu files
endif

# You can modify these variables, some will be appended to by the runtime makefile
INC_FLAGS	?=
CC_FLAGS	?=
NVCC_FLAGS	?=
GASNET_FLAGS	?=
LD_FLAGS	?=

###########################################################################
#
#   Don't change anything below here
#   
###########################################################################

include $(LG_RT_DIR)/runtime.mk

