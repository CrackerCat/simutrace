# simple makefile
#
# Copyright 2014 (C) Karlsruhe Institute of Technology (KIT)
# Marc Rittinghaus, Thorsten Groeninger
#
#             _____ _                 __
#            / ___/(_)___ ___  __  __/ /__________ _________
#            \__ \/ / __ `__ \/ / / / __/ ___/ __ `/ ___/ _ \
#           ___/ / / / / / / / /_/ / /_/ /  / /_/ / /__/  __/
#          /____/_/_/ /_/ /_/\__,_/\__/_/   \__,_/\___/\___/
#                         http://simutrace.org
#
# Simple sample (simple) is part of Simutrace.
#
# simple is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
#
# simple is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with simple. If not, see <http://www.gnu.org/licenses/>.
#

# Base

set(SOURCE_FILES_BASE
    "main.cpp")

# Others

set(OTHER_FILES_OTHERS
    "CMakeLists.txt")


# Source Code Grouping --------------------------------------------------------

set(SOURCE_FILES
    ${SOURCE_FILES_BASE})

set(OTHER_FILES
    ${OTHER_FILES_OTHERS})

source_group("Source files" FILES ${SOURCE_FILES})

source_group("" FILES ${OTHER_FILES})


# Build -----------------------------------------------------------------------

if(BUILD_SAMPLES)
    set(simple_GUID_CMAKE "94C6D044-D4CD-415A-9DEA-897D2238AF16" CACHE INTERNAL "simple GUID")

    add_executable(simple ${SOURCE_FILES})

    target_link_libraries(simple
                          libsimutrace)

    append_target_property(simple FOLDER "Samples")
    set_sdl_compilation(simple)

endif()