qt_add_plugin(dtkbuiltin
    dbuiltiniconengine.cpp dbuiltiniconengine.h
    main.cpp
)
target_link_libraries(dtkbuiltin PRIVATE
    Qt::Core
    Qt::Gui
    Qt::GuiPrivate
    dtkgui
)

install(TARGETS dtkbuiltin
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    FRAMEWORK DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
