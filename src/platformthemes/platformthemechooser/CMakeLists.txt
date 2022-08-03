qt_add_plugin(qdeepin
    ../../dpluginloader.h
    main.cpp
)
target_include_directories(qdeepin PRIVATE
    ../..
)

target_compile_definitions(qdeepin PRIVATE
    BASED_DTK_DIR=\\\"\\\"
    TARGET=\\\"libqdeepin\\\"
)

target_link_libraries(qdeepin PRIVATE
    Qt::Core
    Qt::Gui
    dl
)

if((QT_VERSION_MAJOR GREATER 4))
    target_link_libraries(qdeepin PRIVATE
        Qt::GuiPrivate
    )
endif()

install(TARGETS qdeepin
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    FRAMEWORK DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
