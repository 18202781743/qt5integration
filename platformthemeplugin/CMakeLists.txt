qt_add_plugin(qdeepin
    diconproxyengine.cpp diconproxyengine.h
    dthemesettings.cpp dthemesettings.h
    main.cpp
    qdeepinfiledialoghelper.cpp qdeepinfiledialoghelper.h
    qdeepintheme.cpp qdeepintheme.h
    xdgiconenginecreator.cpp xdgiconenginecreator.h
)
target_include_directories(qdeepin PRIVATE
    (() --variable includedir Qt5XdgIconLoader)
    /qt5xdgiconloader/(() --modversion Qt5XdgIconLoader)
)

target_compile_definitions(qdeepin PRIVATE
    XDG_ICON_VERSION_MAR=(XDG_ICON_VERSION_LIST)
)

target_link_libraries(qdeepin PRIVATE
    Qt::Core
    Qt::CorePrivate
    Qt::DBus
    Qt::Gui
    Qt::GuiPrivate
    Qt::X11Extras
    dtkgui
)


# Resources:
set_source_files_properties("icons/icons/button_voice_active_30px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/button_voice_active_30px.svg/normal.svg"
)
set_source_files_properties("icons/icons/button_voice_active_press_30px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/button_voice_active_30px.svg/selected.svg"
)
set(deepin-theme-plugin-icons_resource_files
    "icons/actions/edit-copy_16px.svg"
    "icons/actions/edit-cut_16px.svg"
    "icons/actions/edit-delete_16px.svg"
    "icons/actions/edit-paste_16px.svg"
    "icons/actions/edit-redo_16px.svg"
    "icons/actions/edit-select-all_16px.svg"
    "icons/actions/edit-undo_16px.svg"
    "icons/icons/button_voice_active_30px.svg"
    "icons/icons/button_voice_active_press_30px.svg"
    "icons/icons/icon_fail_128px.svg"
    "icons/icons/icon_success_128px.svg"
    "icons/texts/audio-volume-left_24px.svg"
    "icons/texts/audio-volume-low_24px.svg"
    "icons/texts/audio-volume-medium_24px.svg"
    "icons/texts/audio-volume-muted_24px.svg"
    "icons/texts/audio-volume-right_24px.svg"
    "icons/texts/button_add_20px.svg"
    "icons/texts/button_reduce_12px.svg"
    "icons/texts/caps_lock_16px.svg"
    "icons/texts/checked_20px.svg"
    "icons/texts/combobox_arrow_12px.svg"
    "icons/texts/edit_12px.svg"
    "icons/texts/fork_indicator_24px.svg"
    "icons/texts/go-down_12px.svg"
    "icons/texts/go-next_12px.svg"
    "icons/texts/go-previous_12px.svg"
    "icons/texts/go-up_12px.svg"
    "icons/texts/lock_indicator_24px.svg"
    "icons/texts/mark_indicator_12px.svg"
    "icons/texts/media-playback-pause_24px.svg"
    "icons/texts/media-playback-start_24px.svg"
    "icons/texts/media-skip-backward_24px.svg"
    "icons/texts/media-skip-forward_24px.svg"
    "icons/texts/next_indicator_24px.svg"
    "icons/texts/password_hide_24px.svg"
    "icons/texts/password_show_24px.svg"
    "icons/texts/prev_indicator_24px.svg"
    "icons/texts/search_indicator_36px.svg"
    "icons/texts/selected_checked_indicator_16px.svg"
    "icons/texts/selected_indicator_16px.svg"
    "icons/texts/selected_indicator_16px.svg.background"
    "icons/texts/unchecked_20px.svg"
    "icons/texts/unlock_indicator_24px.svg"
    "icons/texts/unselected_indicator_16px.svg"
    "icons/texts/window-close_round_30px.svg"
)

qt_add_resources(qdeepin "deepin-theme-plugin-icons"
    PREFIX
        "/icons/deepin/builtin"
    BASE
        "icons"
    FILES
        ${deepin-theme-plugin-icons_resource_files}
)
set_source_files_properties("icons/icons/light/button_voice_30px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/button_voice_30px.svg/normal.svg"
)
set_source_files_properties("icons/icons/light/button_voice_press_30px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/button_voice_30px.svg/selected.svg"
)
set_source_files_properties("icons/icons/light/edit-clear_30px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/button_edit-clear_30px.svg/normal.svg"
)
set_source_files_properties("icons/icons/light/edit-clear_press_30px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/button_edit-clear_30px.svg/selected.svg"
)
set_source_files_properties("icons/icons/light/list_add_16px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/list_add_16px.svg"
)
set_source_files_properties("icons/icons/light/list_delete_16px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/list_delete_16px.svg"
)
set_source_files_properties("icons/icons/light/window-close_round_30px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/window-close_round_30px.svg/normal.svg"
)
set_source_files_properties("icons/icons/light/window-close_round_press_30px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/window-close_round_30px.svg/selected.svg"
)
set(deepin-theme-plugin-icons1_resource_files
    "icons/icons/light/button_voice_30px.svg"
    "icons/icons/light/button_voice_press_30px.svg"
    "icons/icons/light/edit-clear_30px.svg"
    "icons/icons/light/edit-clear_press_30px.svg"
    "icons/icons/light/list_add_16px.svg"
    "icons/icons/light/list_delete_16px.svg"
    "icons/icons/light/window-close_round_30px.svg"
    "icons/icons/light/window-close_round_press_30px.svg"
)

qt_add_resources(qdeepin "deepin-theme-plugin-icons1"
    PREFIX
        "/icons/deepin/builtin/light"
    BASE
        "icons"
    FILES
        ${deepin-theme-plugin-icons1_resource_files}
)
set_source_files_properties("icons/icons/dark/button_voice_30px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/button_voice_30px.svg/normal.svg"
)
set_source_files_properties("icons/icons/dark/button_voice_press_30px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/button_voice_30px.svg/selected.svg"
)
set_source_files_properties("icons/icons/dark/edit-clear_30px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/button_edit-clear_30px.svg/normal.svg"
)
set_source_files_properties("icons/icons/dark/edit-clear_press_30px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/button_edit-clear_30px.svg/selected.svg"
)
set_source_files_properties("icons/icons/dark/list_add_16px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/list_add_16px.svg"
)
set_source_files_properties("icons/icons/dark/list_delete_16px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/list_delete_16px.svg"
)
set_source_files_properties("icons/icons/dark/window-close_round_30px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/window-close_round_30px.svg/normal.svg"
)
set_source_files_properties("icons/icons/dark/window-close_round_press_30px.svg"
    PROPERTIES QT_RESOURCE_ALIAS "icons/window-close_round_30px.svg/selected.svg"
)
set(deepin-theme-plugin-icons2_resource_files
    "icons/icons/dark/button_voice_30px.svg"
    "icons/icons/dark/button_voice_press_30px.svg"
    "icons/icons/dark/edit-clear_30px.svg"
    "icons/icons/dark/edit-clear_press_30px.svg"
    "icons/icons/dark/list_add_16px.svg"
    "icons/icons/dark/list_delete_16px.svg"
    "icons/icons/dark/window-close_round_30px.svg"
    "icons/icons/dark/window-close_round_press_30px.svg"
)

qt_add_resources(qdeepin "deepin-theme-plugin-icons2"
    PREFIX
        "/icons/deepin/builtin/dark"
    BASE
        "icons"
    FILES
        ${deepin-theme-plugin-icons2_resource_files}
)
set(deepin-theme-plugin_resource_files
    "qtquickcontrols2.conf"
)

qt_add_resources(qdeepin "deepin-theme-plugin"
    PREFIX
        "/"
    FILES
        ${deepin-theme-plugin_resource_files}
)

if(((QT_VERSION_MAJOR GREATER 4)) AND ((QT_VERSION_MAJOR GREATER 5) OR (QT_VERSION_MINOR GREATER 7)))
    target_link_libraries(qdeepin PRIVATE
        Qt::ThemeSupportPrivate
    )
endif()

if(((QT_VERSION_MAJOR GREATER 4)) AND (NOT ((QT_VERSION_MAJOR GREATER 5) OR (QT_VERSION_MINOR GREATER 7))))
    target_link_libraries(qdeepin PRIVATE
        platformsupportPrivate
    )
endif()

if(qtCompileTest(dthemed_icon_lookup))
    target_sources(qdeepin PUBLIC
        diconengine.cpp diconengine.h
    )

    target_compile_definitions(qdeepin PRIVATE
        DTHEMED_ICON_LOOKUP
    )
endif()

if(CMAKE_BUILD_TYPE STREQUAL Release)
    target_compile_definitions(qdeepin PRIVATE
        QT_NO_DEBUG_OUTPUT
    )
endif()

install(TARGETS qdeepin
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    FRAMEWORK DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
