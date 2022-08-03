qt_add_executable(tests WIN32
    ../iconengineplugins/builtinengine/dbuiltiniconengine.cpp ../iconengineplugins/builtinengine/dbuiltiniconengine.h
    ../iconengineplugins/svgiconengine/qsvgiconengine.cpp ../iconengineplugins/svgiconengine/qsvgiconengine.h
    ../imageformatplugins/svg/qsvgiohandler.cpp ../imageformatplugins/svg/qsvgiohandler.h
    ../styleplugins/chameleon/chameleonstyle.cpp ../styleplugins/chameleon/chameleonstyle.h
    ../styleplugins/chameleon/common.h
    iconengines/builtinengine/ut_builtinengine.cpp
    iconengines/svgiconengine/ut_qsvgiconengine.cpp
    imageformats/svg/ut_qsvgiohandler.cpp
    main.cpp
)
target_include_directories(tests PRIVATE
    iconengines/builtinengine/../../../iconengineplugins/builtinengine
    iconengines/svgiconengine/../../../iconengineplugins/svgiconengine
    imageformats/svg/../../../imageformatplugins/svg
    styleplugins/chameleon/../../../styleplugins/chameleon
)

target_compile_definitions(tests PRIVATE
    UT_PLATFORMPLUGIN_PATH=\\\"${CMAKE_CURRENT_SOURCE_DIR}/../bin/plugins/platformthemes/\\\"
)

target_link_libraries(tests PRIVATE
    Qt::Concurrent
    Qt::Core
    Qt::Gui
    dtkgui
    dtkwidget
)

target_compile_options(tests
    -fno-access-control
)


# Resources:
set(theme-icons_resource_files
    "iconengines/builtinengine/icons/actions/icon_Layout_16px.svg"
)

qt_add_resources(tests "theme-icons"
    PREFIX
        "/icons/deepin/builtin"
    BASE
        "iconengines/builtinengine/icons"
    FILES
        ${theme-icons_resource_files}
)
set(icons_resource_files
    "iconengines/svgiconengine/icon_window_16px.svg"
)

qt_add_resources(tests "icons"
    PREFIX
        "/"
    BASE
        "iconengines/svgiconengine"
    FILES
        ${icons_resource_files}
)

if(UNIX)
    target_link_libraries(tests PRIVATE
        # Remove: L${CMAKE_CURRENT_SOURCE_DIR}/../../../bin/plugins/styles/
        chameleon
        gtest
    )
endif()

if(CMAKE_BUILD_TYPE STREQUAL Debug)
    target_compile_definitions(tests PRIVATE
        NDEBUG
    )

    target_link_libraries(tests PRIVATE
        gmock
        gtest
    )

    target_compile_options(tests
        -O2
        -Wall
        -fprofile-arcs
        -fsanitize-recover=address
        -fsanitize=address
        -ftest-coverage
        -g
    )
endif()

if(NOT QMAKE_HOST.arch___contains___mips._x_)
    target_sources(tests PUBLIC
        styleplugins/chameleon/ut_chameleonstyle.cpp
    )
endif()

install(TARGETS tests
    BUNDLE DESTINATION .
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)

# Consider using qt_generate_deploy_app_script() for app deployment if
# the project can use Qt 6.3. In that case rerun qmake2cmake with
# --min-qt-version=6.3.
