project(UbuntuSettingsFingerprintQml)

include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_BINARY_DIR}
)
add_definitions(-DUBUNTUSETTINGSFINGERPRINT_LIBRARY)
QT5_ADD_RESOURCES(assets assets.qrc)
add_library(UbuntuSettingsFingerprintQml MODULE
    plugin.cpp
    ubuntusettingsfingerprint.cpp
    ${assets}
)
target_link_libraries(UbuntuSettingsFingerprintQml Qt5::Core Qt5::Qml Qt5::Quick)
add_usc_plugin(Ubuntu.Settings.Fingerprint 0.1 Ubuntu/Settings/Fingerprint TARGETS UbuntuSettingsFingerprintQml)
