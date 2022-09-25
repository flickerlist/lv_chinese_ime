file(GLOB_RECURSE APP_SOURCES src/*.c)

if(ESP_PLATFORM)
  idf_component_register(SRCS ${APP_SOURCES} INCLUDE_DIRS .)
  return()
else()
  include_directories(lv_chinese_ime PUBLIC .)
  add_library(lv_chinese_ime ${APP_SOURCES})
endif()
