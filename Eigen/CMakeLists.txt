cmake_minimum_required(VERSION 2.8.3)
project(EigenTutorial)
add_compile_options(-std=c++11)

set(CMAKE_AUTOMOC ON)
set(CMAKE_INCLUDE_CURRENT_DIR ON)





include_directories(
    ./eigen/    # 若你的Eigen不是这个目录，请把此目录改为你的位置
    ./Chapter1_DenseMatrixAndArray/
    ./Chapter2_DenseLinearProblemsAndDecompositions/
    ./Chapter3_SparseLinearAlgebra/
    )

add_executable(chapter1_test chapter1_test.cpp)  #编译第一章

add_executable(chapter2_test chapter2_test.cpp)  #编译第二章


add_executable(chapter3_test chapter3_test.cpp)  #编译第三章
if(${USE_QT5})
target_link_libraries(chapter3_test ${Qt5Widgets_LIBRARIES} )
else()
target_link_libraries(chapter3_test  Qt4::QtGui )
endif()


add_executable(chapter4_test chapter4_test.cpp) # 编译第四章，请注意，第四章是我随便写了几行代码测试玩的