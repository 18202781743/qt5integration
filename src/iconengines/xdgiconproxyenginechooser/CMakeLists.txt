qt_add_plugin(xdgicon
    ../../dpluginloader.h
    main.cpp
)
target_include_directories(xdgicon PRIVATE
    ../..
)

target_compile_definitions(xdgicon PRIVATE
    BASED_DTK_DIR=\\\"\\\"
    TARGET=\\\"libxdgicon\\\"
)

target_link_libraries(xdgicon PRIVATE
    Qt::Core
    Qt::Gui
    dl
)

install(TARGETS xdgicon
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    FRAMEWORK DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
