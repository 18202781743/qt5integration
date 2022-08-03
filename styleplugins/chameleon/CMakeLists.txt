qt_add_plugin(chameleon
    ../dstyleplugin/dstyleanimation.cpp ../dstyleplugin/dstyleanimation.h
    chameleonstyle.cpp chameleonstyle.h
    common.h
    main.cpp
)
target_link_libraries(chameleon PRIVATE
    Qt::Core
    Qt::CorePrivate
    Qt::Gui
    Qt::GuiPrivate
    Qt::Widgets
    Qt::WidgetsPrivate
    dtkgui
    dtkwidget
)


# Resources:
set(resources_resource_files
    "menu_shadow.svg"
)

qt_add_resources(chameleon "resources"
    PREFIX
        "/chameleon"
    FILES
        ${resources_resource_files}
)

install(TARGETS chameleon
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    FRAMEWORK DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
