qt_add_plugin(chameleon
    ../../dpluginloader.h
    main.cpp
)
target_include_directories(chameleon PRIVATE
    ../..
)

target_compile_definitions(chameleon PRIVATE
    BASED_DTK_DIR=\\\"\\\"
    TARGET=\\\"libchameleon\\\"
)

target_link_libraries(chameleon PRIVATE
    Qt::Core
    Qt::Gui
    Qt::Widgets
    dl
)

install(TARGETS chameleon
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    FRAMEWORK DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
