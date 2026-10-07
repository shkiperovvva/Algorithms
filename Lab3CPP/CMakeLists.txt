add_executable(Lab3CPP task.cpp)

target_include_directories(Lab3CPP PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/../LibraryCPP
)

target_link_libraries(Lab3CPP PRIVATE LibraryCPP)

add_test(
    NAME TestLab3
    COMMAND Lab3CPP ${CMAKE_CURRENT_SOURCE_DIR}/input.txt
)

set_tests_properties(TestLab3 PROPERTIES
    PASS_REGULAR_EXPRESSION "3\n# 2 5\n# # 1 4 1\n3 2 # 2 3 2 3\n1 2 3 4 1\n3 4 5\n5"
)

# входные данные для теста из задания:
#      3
#    8 2 5
#  6 7 1 4 1
#3 2 5 2 3 2 3
#  1 2 3 4 1
#    3 4 5
#      5

# выходные данные:
#      3
#    # 2 5
#  # # 1 4 1
#3 2 # 2 3 2 3
#  1 2 3 4 1
#    3 4 5
#      5

