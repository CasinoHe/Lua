CMAKE_MINIMUM_REQUIRED(VERSION 3.10)

project(lua C)

set(SRC_ROOT_DIR ${CMAKE_SOURCE_DIR})

set(CORE_FILES
	${SRC_ROOT_DIR}/lapi.c
	${SRC_ROOT_DIR}/lcode.c
	${SRC_ROOT_DIR}/lctype.c
	${SRC_ROOT_DIR}/ldebug.c
	${SRC_ROOT_DIR}/ldo.c
	${SRC_ROOT_DIR}/ldump.c
	${SRC_ROOT_DIR}/lfunc.c
	${SRC_ROOT_DIR}/lgc.c
	${SRC_ROOT_DIR}/llex.c
	${SRC_ROOT_DIR}/lmem.c
	${SRC_ROOT_DIR}/lobject.c
	${SRC_ROOT_DIR}/lopcodes.c
	${SRC_ROOT_DIR}/lparser.c
	${SRC_ROOT_DIR}/lstate.c
	${SRC_ROOT_DIR}/lstring.c
	${SRC_ROOT_DIR}/ltable.c
	${SRC_ROOT_DIR}/ltm.c
	${SRC_ROOT_DIR}/lundump.c
	${SRC_ROOT_DIR}/lvm.c
	${SRC_ROOT_DIR}/lzio.c
)

set(LIB_FILES
	${SRC_ROOT_DIR}/lauxlib.c
	${SRC_ROOT_DIR}/lbaselib.c
	${SRC_ROOT_DIR}/lbitlib.c
	${SRC_ROOT_DIR}/lcorolib.c
	${SRC_ROOT_DIR}/ldblib.c
	${SRC_ROOT_DIR}/liolib.c
	${SRC_ROOT_DIR}/lmathlib.c
	${SRC_ROOT_DIR}/loslib.c
	${SRC_ROOT_DIR}/lstrlib.c
	${SRC_ROOT_DIR}/ltablib.c
	${SRC_ROOT_DIR}/lutf8lib.c
	${SRC_ROOT_DIR}/loadlib.c
	${SRC_ROOT_DIR}/linit.c
)

set(EXECUTABLE_FILES
	${SRC_ROOT_DIR}/lua.c
	# ${SRC_ROOT_DIR}/luac.c
)

add_executable(${PROJECT_NAME} ${EXECUTABLE_FILES} ${CORE_FILES} ${LIB_FILES})
target_compile_definitions(${PROJECT_NAME} PRIVATE -DLUA_COMPAT_5_2)
