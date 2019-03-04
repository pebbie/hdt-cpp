SET(LIBS hdt)
include_directories(. ../src/util)

add_executable(hdt2rdf hdt2rdf.cpp)
target_link_libraries(hdt2rdf ${LIBS})
install(TARGETS hdt2rdf DESTINATION bin)

add_executable(hdtInfo hdtInfo.cpp)
target_link_libraries(hdtInfo ${LIBS})
install(TARGETS hdtInfo DESTINATION bin)

add_executable(hdtSearch hdtSearch.cpp)
target_link_libraries(hdtSearch ${LIBS})
install(TARGETS hdtSearch DESTINATION bin)

add_executable(modifyHeader modifyHeader.cpp)
target_link_libraries(modifyHeader ${LIBS})
install(TARGETS modifyHeader DESTINATION bin)

add_executable(rdf2hdt rdf2hdt.cpp)
target_link_libraries(rdf2hdt ${LIBS})
install(TARGETS rdf2hdt DESTINATION bin)

add_executable(replaceHeader replaceHeader.cpp)
target_link_libraries(replaceHeader ${LIBS})
install(TARGETS replaceHeader DESTINATION bin)

add_executable(searchHeader searchHeader.cpp)
target_link_libraries(searchHeader ${LIBS})
install(TARGETS searchHeader DESTINATION bin)