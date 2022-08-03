qt_add_plugin(dsvg
    main.cpp
    qsvgiohandler.cpp qsvgiohandler.h
)
target_link_libraries(dsvg PRIVATE
    Qt::Core
    Qt::Gui
)

install(TARGETS dsvg
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    FRAMEWORK DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
