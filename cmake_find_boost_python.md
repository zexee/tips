CMake find python3
===

Find Python3
---
    find_package(Python3 REQUIRED CONPONENTS Development)
    include_directories(${Python3_INCLUDE_DIRS})  # boost.python need this
   
Find Boost.Python
---
    set(Boost_USE_STATIC_LIBS ON)  # link to static boost
    set(BOOST_INCLUDEDIR /usr/local/include)  # to boost include directory
    set(BOOST_LIBRARYDIR /usr/local/lib)  # to boost lib directory
    find_package(Boost REQUIRED COMPONENTS python36 numpy36)  # corresponding to lib filename
    link_libraries(${Boost_PYTHON36_LIBRARY} ${Boost_NUMPY36_LIBRARY})  # corresponding to package name

