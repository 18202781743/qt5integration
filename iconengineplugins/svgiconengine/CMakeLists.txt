qt_add_plugin(dsvgicon
    main.cpp
    qsvgiconengine.cpp qsvgiconengine.h
)
target_link_libraries(dsvgicon PRIVATE
    Qt::Concurrent
    Qt::Core
    Qt::Gui
    Qt::GuiPrivate
    dtkgui
)

install(TARGETS dsvgicon
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    FRAMEWORK DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
