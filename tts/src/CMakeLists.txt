project(tts_multilingual)
include_directories (.)
IF(MSVC)
    ADD_DEFINITIONS(/D _CRT_SECURE_NO_WARNINGS)
ENDIF(MSVC)
link_directories(../../../lib)
add_executable(tts main.cpp) 
add_executable(tts_client Socket.cpp Socket_Cliente.cpp Cliente.cpp)
add_executable(tts_server Socket.cpp Socket_Servidor.cpp Servidor.cpp)
#SET_TARGET_PROPERTIES(tts PROPERTIES LINKER_LANGUAGE CXX)
target_link_libraries(tts htts)
target_link_libraries(tts_client htts)
target_link_libraries(tts_server htts)
INSTALL_TARGETS(/bin tts tts_client tts_server)
