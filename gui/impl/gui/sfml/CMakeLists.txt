set(TARGET_DIR ${PROJECT_SOURCE_DIR}/gui/impl/gui/sfml)
set(SRCROOT ${TARGET_DIR}/src)
include_directories(${PROJECT_SOURCE_DIR}/include)
include_directories(${SFML_INCLUDE_DIR})

add_library(lxgui-sfml STATIC
    ${SRCROOT}/gui_sfml_font.cpp
    ${SRCROOT}/gui_sfml_renderer.cpp
    ${SRCROOT}/gui_sfml_material.cpp
    ${SRCROOT}/gui_sfml_rendertarget.cpp
    ${SRCROOT}/gui_sfml.cpp
)

file(GLOB files ${PROJECT_SOURCE_DIR}/include/lxgui/impl/gui_sfml*.hpp)
install(FILES ${files} DESTINATION include/lxgui/impl)
install(TARGETS lxgui-sfml ARCHIVE DESTINATION lib)

