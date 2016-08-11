# Group the sources

source_group ("INFOFILES" FILES "*.h")
source_group ("RESFILE" FILES "*.rc")

# Check if we are on UNIX
if(UNIX)
    source_group ("SRCFILES" FILES api_hook.cpp api_info.cpp commands_meta.cpp conf_meta.cpp
        dllapi.cpp engine_api.cpp engineinfo.cpp game_support.cpp
        game_autodetect.cpp h_export.cpp linkgame.cpp linkplug.cpp
        log_meta.cpp meta_eiface.cpp metamod.cpp mlist.cpp mplayer.cpp
        mplugin.cpp mqueue.cpp mreg.cpp mutil.cpp osdep.cpp
        osdep_p.cpp reg_support.cpp sdk_util.cpp studioapi.cpp
        support_meta.cpp thread_logparse.cpp vdate.cpp osdep_linkent_linux.cpp 
        osdep_detect_gamedll_linux.cpp)
elseif(WIN32)
    source_group ("SRCFILES" FILES api_hook.cpp api_info.cpp commands_meta.cpp conf_meta.cpp
        dllapi.cpp engine_api.cpp engineinfo.cpp game_support.cpp
        game_autodetect.cpp h_export.cpp linkgame.cpp linkplug.cpp
        log_meta.cpp meta_eiface.cpp metamod.cpp mlist.cpp mplayer.cpp
        mplugin.cpp mqueue.cpp mreg.cpp mutil.cpp osdep.cpp
        osdep_p.cpp reg_support.cpp sdk_util.cpp studioapi.cpp
        support_meta.cpp thread_logparse.cpp vdate.cpp osdep_linkent_win32.cpp
        osdep_detect_gamedll_win32.cpp)
    set()
else()
    message(SEND_ERROR "Seems you are running CMake on a unknown OS, to build this project, you should be on Windows or UNIX-like Systems.")
endif()

set(CMAKE_C_FLAGS "-D__INTERNALS_USE_REGPARAMS__")