Clang 6

```
$ cmake -S . -B build_clang6 -DCMAKE_CXX_COMPILER=clang++-6.0 -DCMAKE_C_COMPILER=clang-6.0
-- The C compiler identification is Clang 6.0.1
-- The CXX compiler identification is Clang 6.0.1
-- Check for working C compiler: /usr/bin/clang-6.0
-- Check for working C compiler: /usr/bin/clang-6.0 -- works
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Detecting C compile features
-- Detecting C compile features - done
-- Check for working CXX compiler: /usr/bin/clang++-6.0
-- Check for working CXX compiler: /usr/bin/clang++-6.0 -- works
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done
-- Generating done
-- Build files have been written to: /home/mjcarroll/repro/build_clang6

$ cmake --build build_clang6
Scanning dependencies of target reproduction
[ 25%] Building CXX object CMakeFiles/reproduction.dir/Reproduction.cc.o
[ 50%] Linking CXX shared library libreproduction.so
[ 50%] Built target reproduction
Scanning dependencies of target inline-namespace-repro
[ 75%] Building CXX object CMakeFiles/inline-namespace-repro.dir/main.cc.o
[100%] Linking CXX executable inline-namespace-repro
/usr/bin/ld: CMakeFiles/inline-namespace-repro.dir/main.cc.o: in function `main':
main.cc:(.text+0x10): undefined reference to `foo::bar::v1::baz()'
clang: error: linker command failed with exit code 1 (use -v to see invocation)
make[2]: *** [CMakeFiles/inline-namespace-repro.dir/build.make:85: inline-namespace-repro] Error 1
make[1]: *** [CMakeFiles/Makefile2:78: CMakeFiles/inline-namespace-repro.dir/all] Error 2
make: *** [Makefile:84: all] Error 2
```

Clang 7

```
$ cmake -S . -B build_clang7 -DCMAKE_CXX_COMPILER=clang++-7 -DCMAKE_C_COMPILER=clang-7
-- The C compiler identification is Clang 7.0.1
-- The CXX compiler identification is Clang 7.0.1
-- Check for working C compiler: /usr/bin/clang-7
-- Check for working C compiler: /usr/bin/clang-7 -- works
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Detecting C compile features
-- Detecting C compile features - done
-- Check for working CXX compiler: /usr/bin/clang++-7
-- Check for working CXX compiler: /usr/bin/clang++-7 -- works
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done
-- Generating done
-- Build files have been written to: /home/mjcarroll/repro/build_clang7

$ cmake --build build_clang7
Scanning dependencies of target reproduction
[ 25%] Building CXX object CMakeFiles/reproduction.dir/Reproduction.cc.o
[ 50%] Linking CXX shared library libreproduction.so
[ 50%] Built target reproduction
Scanning dependencies of target inline-namespace-repro
[ 75%] Building CXX object CMakeFiles/inline-namespace-repro.dir/main.cc.o
[100%] Linking CXX executable inline-namespace-repro
[100%] Built target inline-namespace-repro
```
