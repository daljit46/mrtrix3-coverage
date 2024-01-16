# MRtrix3 CPP coverage

Code coverage analysis using `gcov` and `gcovr`.

Instructions used:

```
cmake
-B build
-G Ninja
-D CMAKE_BUILD_TYPE=Debug
-D CMAKE_CXX_FLAGS="-fprofile-arcs -ftest-coverage"
-D COVERAGE_EXTRA_FLAGS="-l -p"

cmake --build build

ctest -R bin -T test -T coverage --test-dir build

mkdir html && gcovr --html --html-details -o html/coverage.html
```