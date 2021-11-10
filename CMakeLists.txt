
set(IMGUI_SOURCES
  imgui.cpp
  imgui_demo.cpp
  imgui_draw.cpp
  imgui_tables.cpp
  imgui_widgets.cpp
  backends/imgui_impl_vulkan.cpp
  backends/imgui_impl_sdl.cpp)

set(IMGUI_HEADERS
  imconfig.h
  imgui.h
  backends/imgui_impl_sdl.h
  backends/imgui_impl_vulkan.h
  imgui_internal.h
  imstb_rectpack.h
  imstb_textedit.h
  imstb_truetype.h)

add_library(imgui STATIC ${IMGUI_SOURCES} ${IMGUI_HEADERS})
target_include_directories(imgui PUBLIC .)
target_link_libraries(imgui Vulkan::Vulkan SDL2::SDL2main SDL2::SDL2-static)
