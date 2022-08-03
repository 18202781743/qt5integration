qt_add_executable(styles WIN32 MACOSX_BUNDLE
    main.cpp
    norwegianwoodstyle.cpp norwegianwoodstyle.h
    widgetgallery.cpp widgetgallery.h
)
target_link_libraries(styles PRIVATE
    Qt::Core
    Qt::Gui
    Qt::Widgets
    dtkwidget
)


# Resources:
set(styles_resource_files
    "images/woodbackground.png"
    "images/woodbutton.png"
)

qt_add_resources(styles "styles"
    PREFIX
        "/"
    FILES
        ${styles_resource_files}
)

install(TARGETS styles
    BUNDLE DESTINATION .
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)

# Consider using qt_generate_deploy_app_script() for app deployment if
# the project can use Qt 6.3. In that case rerun qmake2cmake with
# --min-qt-version=6.3.
