qt_add_plugin(dsvg
    ../../dpluginloader.h
    main.cpp
)
target_include_directories(dsvg PRIVATE
    ../..
)

target_compile_definitions(dsvg PRIVATE
    BASED_DTK_DIR=\\\"\\\"
    TARGET=\\\"libdsvg\\\"
)

target_link_libraries(dsvg PRIVATE
    Qt::Core
    Qt::Gui
    dl
)

install(TARGETS dsvg
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    FRAMEWORK DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
