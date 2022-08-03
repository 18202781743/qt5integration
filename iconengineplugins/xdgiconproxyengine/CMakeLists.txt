qt_add_plugin(xdgicon
    main.cpp
    xdgiconproxyengine.cpp xdgiconproxyengine.h
)
target_include_directories(xdgicon PRIVATE
    (() --variable includedir Qt5XdgIconLoader)
    /qt5xdgiconloader/(() --modversion Qt5XdgIconLoader)
)

target_compile_definitions(xdgicon PRIVATE
    QT_DEPRECATED_WARNINGS
    XDG_ICON_VERSION_MAR=(XDG_ICON_VERSION_LIST)
)

target_link_libraries(xdgicon PRIVATE
    Qt::Core
    Qt::Gui
    Qt::GuiPrivate
)

install(TARGETS xdgicon
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    FRAMEWORK DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
