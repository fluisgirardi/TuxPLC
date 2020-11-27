cmake_minimum_required(VERSION 3.1)
project(tuxeip)
set(tuxeip_VERSION_MAJOR 1)
set(tuxeip_VERSION_MINOR 0)
set(CMAKE_C_FLAGS "-fPIC")

add_library(tuxeip SHARED
	src/AB.c
	src/CIP_IOI.c
	src/CM.c
	src/ErrCodes.c
	src/Ethernet_IP.c
	src/LGX.c
	src/MR.c
	src/PLC.c
	src/SendData.c
)

set_target_properties(tuxeip PROPERTIES PUBLIC_HEADER "src/TuxDef.h;src/CM.h;src/TuxEip.h;src/ErrCodes.h;src/MR.h;src/EIP_Const.h;src/SendData.h;src/CIP_Const.h;src/CIP_IOI.h;src/AB.h;src/LGX.h;src/PLC.h;src/CIP_Types.h;src/CIP_Objects.h;src/Ethernet_IP.h")

install(
	TARGETS tuxeip
	LIBRARY DESTINATION lib
	PUBLIC_HEADER DESTINATION include/tuxeip
)
