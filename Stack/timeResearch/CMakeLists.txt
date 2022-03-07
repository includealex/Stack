find_package(benchmark REQUIRED)

add_executable(stack_bench find_time.cpp)
target_link_libraries(stack_bench stack benchmark::benchmark)

add_custom_target(run_stack_bench
		  COMMENT "Running benchmark"
		  COMMAND ./stack_bench)

add_dependencies(run_stack_bench stack_bench stack)