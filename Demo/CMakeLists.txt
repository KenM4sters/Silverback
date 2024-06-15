add_executable(SilverbackDemo main.cpp)

target_include_directories(SilverbackDemo 
PUBLIC ${CMAKE_SOURCE_DIR}/Sources/
PUBLIC ${CMAKE_SOURCE_DIR}/External/GLFW/include/
PUBLIC ${CMAKE_SOURCE_DIR}/External/Glad/include/
)

target_link_libraries(SilverbackDemo glfw glad)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fsanitize=address -fno-omit-frame-pointer")
set(CMAKE_LINKER_FLAGS "${CMAKE_LINKER_FLAGS} -fsanitize=address")

#add_test(NAME SilverbackUnitTests COMMAND SilverbackUnitTests --gtest_color=yes --gtest_output=xml:report.xml --gtest_print_time)