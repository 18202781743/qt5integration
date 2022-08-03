qt_add_plugin(dsvgicon
    ../../dpluginloader.h
    main.cpp
)
target_include_directories(dsvgicon PRIVATE
    ../..
)

target_compile_definitions(dsvgicon PRIVATE
    BASED_DTK_DIR=\\\"\\\"
    TARGET=\\\"libdsvgicon\\\"
)

target_link_libraries(dsvgicon PRIVATE
    Qt::Core
    Qt::Gui
    dl
)

install(TARGETS dsvgicon
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    FRAMEWORK DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
