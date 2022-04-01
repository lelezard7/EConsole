cmake_minimum_required(VERSION 3.5)
project(PDCurses LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(files
    pdcurses/addch.c
    pdcurses/addchstr.c
    pdcurses/addstr.c
    pdcurses/attr.c
    pdcurses/beep.c
    pdcurses/bkgd.c
    pdcurses/border.c
    pdcurses/clear.c
    pdcurses/color.c
    pdcurses/debug.c
    pdcurses/delch.c
    pdcurses/deleteln.c
    pdcurses/getch.c
    pdcurses/getstr.c
    pdcurses/getyx.c
    pdcurses/inch.c
    pdcurses/inchstr.c
    pdcurses/initscr.c
    pdcurses/inopts.c
    pdcurses/insch.c
    pdcurses/insstr.c
    pdcurses/instr.c
    pdcurses/kernel.c
    pdcurses/keyname.c
    pdcurses/mouse.c
    pdcurses/move.c
    pdcurses/outopts.c
    pdcurses/overlay.c
    pdcurses/pad.c
    pdcurses/panel.c
    pdcurses/printw.c
    pdcurses/refresh.c
    pdcurses/scanw.c
    pdcurses/scroll.c
    pdcurses/scr_dump.c
    pdcurses/slk.c
    pdcurses/termattr.c
    pdcurses/touch.c
    pdcurses/util.c
    pdcurses/window.c

    wincon/pdcclip.c
    wincon/pdcdisp.c
    wincon/pdcgetsc.c
    wincon/pdckbd.c
    wincon/pdcscrn.c
    wincon/pdcsetsc.c
    wincon/pdcutil.c)

set(LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})
set(BUILD_SHARED_LIBS ON)
add_library(PDCurses SHARED ${files})
target_include_directories(PDCurses PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
