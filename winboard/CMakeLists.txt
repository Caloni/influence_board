cmake_minimum_required(VERSION 3.16)

include_directories(. .. extends/infboard)
add_compile_definitions(_WIN32_WINNT=_WIN32_WINNT_WIN2K)

project (winboard)

add_executable(winboard WIN32
  ../backend.c
  #../childio.c
  ../gamelist.c
  ../lists.c
  ../moves.c
  ../pgntags.c
  #../xboard.c
  #../xedittags.c
  #../xgamelist.c
  #../xhistory.c
  #../zic2xpm.c
  ../zippy.c
  ../acconfig.h
  ../backend.h
  ../backendz.h
  ../childio.h
  ../common.h
  ../frontend.h
  ../lists.h
  ../moves.h
  ../parser.h
  ../xboard.h
  ../xedittags.h
  ../xgamelist.h
  ../xhistory.h
  ../zippy.h

  config.h
  defaults.h
  resource.h
  wclipbrd.h
  wedittags.h
  wgamelist.h
  winboard.h
  woptions.h
  wsockerr.h
  parser.c
  wclipbrd.c
  wedittags.c
  wgamelist.c
  winboard.c
  winboard.rc
  woptions.c
  wsockerr.c

  extends/infboard/infboard.h
  extends/infboard/infboard.c
  extends/infboard/main.c
  #extends/infboard/support.c
)

if(WIN32)
  target_link_libraries(winboard wsock32 ws2_32 Winmm)
endif()
