qt_add_plugin(dtkbuiltin
    ../../dpluginloader.h
    main.cpp
)
target_include_directories(dtkbuiltin PRIVATE
    ../..
)

target_compile_definitions(dtkbuiltin PRIVATE
    BASED_DTK_DIR=\\\"\\\"
    TARGET=\\\"libdtkbuiltin\\\"
)

target_link_libraries(dtkbuiltin PRIVATE
    Qt::Core
    Qt::Gui
    dl
)

install(TARGETS dtkbuiltin
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    FRAMEWORK DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
