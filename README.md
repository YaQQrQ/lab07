michel@MichelUbuntu:~$ export GITHUB_USERNAME=MichelsonIU815
michel@MichelUbuntu:~$ alias gsed=sed
michel@MichelUbuntu:~$ cd ${GITHUB_USERNAME}/workspace
michel@MichelUbuntu:~/MichelsonIU815/workspace$ pushd .
~/MichelsonIU815/workspace ~/MichelsonIU815/workspace
michel@MichelUbuntu:~/MichelsonIU815/workspace$ source scripts/activate
michel@MichelUbuntu:~/MichelsonIU815/workspace$ git clone https://github.com/${GITHUB_USERNAME}/lab04 projects/lab05
fatal: целевой путь «projects/lab05» уже существует и не является пустым каталогом.
michel@MichelUbuntu:~/MichelsonIU815/workspace$ git clone https://github.com/${GITHUB_USERNAME}/lab04 projects/lab05
Клонирование в «projects/lab05»...
remote: Enumerating objects: 39, done.
remote: Counting objects: 100% (39/39), done.
remote: Compressing objects: 100% (27/27), done.
remote: Total 39 (delta 10), reused 32 (delta 6), pack-reused 0 (from 0)
Получение объектов: 100% (39/39), 10.74 КиБ | 268.00 КиБ/с, готово.
Определение изменений: 100% (10/10), готово.
michel@MichelUbuntu:~/MichelsonIU815/workspace$ cd projects/lab05
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ git remote remove origin
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab05
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ mkdir third-party
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ git submodule add https://github.com/google/googletest third-party/gtest
Клонирование в «/home/michel/MichelsonIU815/workspace/projects/lab05/third-party/gtest»...
remote: Enumerating objects: 27973, done.
remote: Counting objects: 100% (165/165), done.
remote: Compressing objects: 100% (112/112), done.
remote: Total 27973 (delta 95), reused 59 (delta 49), pack-reused 27808 (from 5)
Получение объектов: 100% (27973/27973), 13.92 МиБ | 3.85 МиБ/с, готово.
Определение изменений: 100% (20700/20700), готово.
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ cd third-party/gtest && git checkout release-1.8.1 && cd ../..
Примечание: переключение на «release-1.8.1».

Вы сейчас в состоянии «отсоединённого указателя HEAD». Можете осмотреться,
внести экспериментальные изменения и зафиксировать их, также можете
отменить любые коммиты, созданные в этом состоянии, не затрагивая другие
ветки, переключившись обратно на любую ветку.

Если хотите создать новую ветку для сохранения созданных коммитов, можете
сделать это (сейчас или позже), используя команду switch с параметром -c.
Например:

  git switch -c <новая-ветка>

Или отмените эту операцию с помощью:

  git switch -

Отключите этот совет, установив переменную конфигурации
advice.detachedHead в значение false

HEAD сейчас на 2fe3bd99 Merge pull request #1433 from dsacre/fix-clang-warnings
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ git add third-party/gtest
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ git commit -m"added gtest framework"
[master ddd6d4f] added gtest framework
 2 files changed, 4 insertions(+)
 create mode 100644 .gitmodules
 create mode 160000 third-party/gtest
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ gsed -i '/option(BUILD_EXAMPLES "Build examples" OFF)/a\
> option(BUILD_TESTS "Build tests" OFF)
> ' CMakeLists.txt
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ cat >> CMakeLists.txt <<EOF
> if(BUILD_TESTS)
  enable_testing()
  add_subdirectory(third-party/gtest)
  file(GLOB \${PROJECT_NAME}_TEST_SOURCES tests/*.cpp)
  add_executable(check \${\${PROJECT_NAME}_TEST_SOURCES})
  target_link_libraries(check \${PROJECT_NAME} gtest_main)
  add_test(NAME check COMMAND check)
endif()
> EOF
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ mkdir tests
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ cat > tests/test1.cpp <<EOF
> #include <print.hpp>

#include <gtest/gtest.h>

TEST(Print, InFileStream)
{
  std::string filepath = "file.txt";
  std::string text = "hello";
  std::ofstream out{filepath};

  print(text, out);
  out.close();

  std::string result;
  std::ifstream in{filepath};
  in >> result;

  EXPECT_EQ(result, text);
}
> EOF
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ cmake -H. -B_build -DBUILD_TESTS=ON
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- The C compiler identification is GNU 9.5.0
-- The CXX compiler identification is GNU 9.5.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
CMake Deprecation Warning at third-party/gtest/CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


CMake Deprecation Warning at third-party/gtest/googlemock/CMakeLists.txt:42 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


CMake Deprecation Warning at third-party/gtest/googletest/CMakeLists.txt:49 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


CMake Warning (dev) at third-party/gtest/googletest/cmake/internal_utils.cmake:239 (find_package):
  Policy CMP0148 is not set: The FindPythonInterp and FindPythonLibs modules
  are removed.  Run "cmake --help-policy CMP0148" for policy details.  Use
  the cmake_policy command to set the policy and suppress this warning.

Call Stack (most recent call first):
  third-party/gtest/googletest/CMakeLists.txt:84 (include)
This warning is for project developers.  Use -Wno-dev to suppress it.

-- Found PythonInterp: /usr/bin/python3 (found version "3.12.3") 
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD - Success
-- Found Threads: TRUE  
-- Configuring done (0.4s)
-- Generating done (0.0s)
-- Build files have been written to: /home/michel/MichelsonIU815/workspace/projects/lab05/_build
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ cmake --build _build
[  8%] Building CXX object CMakeFiles/print.dir/sources/print.cpp.o
[ 16%] Linking CXX static library libprint.a
[ 16%] Built target print
[ 25%] Building CXX object third-party/gtest/googlemock/gtest/CMakeFiles/gtest.dir/src/gtest-all.cc.o
[ 33%] Linking CXX static library libgtest.a
[ 33%] Built target gtest
[ 41%] Building CXX object third-party/gtest/googlemock/gtest/CMakeFiles/gtest_main.dir/src/gtest_main.cc.o
[ 50%] Linking CXX static library libgtest_main.a
[ 50%] Built target gtest_main
[ 58%] Building CXX object CMakeFiles/check.dir/tests/test1.cpp.o
[ 66%] Linking CXX executable check
[ 66%] Built target check
[ 75%] Building CXX object third-party/gtest/googlemock/CMakeFiles/gmock.dir/src/gmock-all.cc.o
[ 83%] Linking CXX static library libgmock.a
[ 83%] Built target gmock
[ 91%] Building CXX object third-party/gtest/googlemock/CMakeFiles/gmock_main.dir/src/gmock_main.cc.o
[100%] Linking CXX static library libgmock_main.a
[100%] Built target gmock_main
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ cmake --build _build --target test
Running tests...
Test project /home/michel/MichelsonIU815/workspace/projects/lab05/_build
    Start 1: check
1/1 Test #1: check ............................   Passed    0.00 sec

100% tests passed, 0 tests failed out of 1

Total Test time (real) =   0.00 sec
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ _build/check
Running main() from /home/michel/MichelsonIU815/workspace/projects/lab05/third-party/gtest/googletest/src/gtest_main.cc
[==========] Running 1 test from 1 test case.
[----------] Global test environment set-up.
[----------] 1 test from Print
[ RUN      ] Print.InFileStream
[       OK ] Print.InFileStream (0 ms)
[----------] 1 test from Print (0 ms total)

[----------] Global test environment tear-down
[==========] 1 test from 1 test case ran. (0 ms total)
[  PASSED  ] 1 test.
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ cmake --build _build --target test -- ARGS=--verbose
Running tests...
UpdateCTestConfiguration  from :/home/michel/MichelsonIU815/workspace/projects/lab05/_build/DartConfiguration.tcl
UpdateCTestConfiguration  from :/home/michel/MichelsonIU815/workspace/projects/lab05/_build/DartConfiguration.tcl
Test project /home/michel/MichelsonIU815/workspace/projects/lab05/_build
Constructing a list of tests
Done constructing a list of tests
Updating test list for fixtures
Added 0 tests to meet fixture requirements
Checking test dependency graph...
Checking test dependency graph end
test 1
    Start 1: check

1: Test command: /home/michel/MichelsonIU815/workspace/projects/lab05/_build/check
1: Working Directory: /home/michel/MichelsonIU815/workspace/projects/lab05/_build
1: Test timeout computed to be: 10000000
1: Running main() from /home/michel/MichelsonIU815/workspace/projects/lab05/third-party/gtest/googletest/src/gtest_main.cc
1: [==========] Running 1 test from 1 test case.
1: [----------] Global test environment set-up.
1: [----------] 1 test from Print
1: [ RUN      ] Print.InFileStream
1: [       OK ] Print.InFileStream (0 ms)
1: [----------] 1 test from Print (0 ms total)
1: 
1: [----------] Global test environment tear-down
1: [==========] 1 test from 1 test case ran. (0 ms total)
1: [  PASSED  ] 1 test.
1/1 Test #1: check ............................   Passed    0.00 sec

100% tests passed, 0 tests failed out of 1

Total Test time (real) =   0.00 sec
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ gsed -i 's/lab04/lab05/g' README.md
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ gsed -i 's/\(DCMAKE_INSTALL_PREFIX=_install\)/\1 -DBUILD_TESTS=ON/' .travis.yml
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ gsed -i '/cmake --build _build --target install/a\
> - cmake --build _build --target test -- ARGS=--verbose
> ' .travis.yml
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ git add .travis.yml
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ git add tests
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$  git add -p
diff --git a/CMakeLists.txt b/CMakeLists.txt
index 96a361e..89739e7 100644
--- a/CMakeLists.txt
+++ b/CMakeLists.txt
@@ -4,6 +4,7 @@ set(CMAKE_CXX_STANDARD 11)
 set(CMAKE_CXX_STANDARD_REQUIRED ON)
 
 option(BUILD_EXAMPLES "Build examples" OFF)
+option(BUILD_TESTS "Build tests" OFF)
 
 project(print)
 
(1/2) Индексировать этот блок [y,n,q,a,d,j,J,g,/,e,?]? y
@@ -34,3 +35,11 @@ install(TARGETS print
 
 install(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/include/ DESTINATION include)
 install(EXPORT print-config DESTINATION cmake)
+if(BUILD_TESTS)
+  enable_testing()
+  add_subdirectory(third-party/gtest)
+  file(GLOB ${PROJECT_NAME}_TEST_SOURCES tests/*.cpp)
+  add_executable(check ${${PROJECT_NAME}_TEST_SOURCES})
+  target_link_libraries(check ${PROJECT_NAME} gtest_main)
+  add_test(NAME check COMMAND check)
+endif()
(2/2) Индексировать этот блок [y,n,q,a,d,K,g,/,e,?]? y

michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ git commit -m"added tests"
[master 0f8f992] added tests
 3 files changed, 30 insertions(+), 1 deletion(-)
 create mode 100644 tests/test1.cpp
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ git push origin master
Username for 'https://github.com': MichelsonIU815
Password for 'https://MichelsonIU815@github.com': 
Перечисление объектов: 49, готово.
Подсчет объектов: 100% (49/49), готово.
При сжатии изменений используется до 12 потоков
Сжатие объектов: 100% (31/31), готово.
Запись объектов: 100% (49/49), 11.79 КиБ | 5.90 МиБ/с, готово.
Всего 49 (изменений 14), повторно использовано 36 (изменений 10), повторно использовано пакетов 0
remote: Resolving deltas: 100% (14/14), done.
remote: error: GH013: Repository rule violations found for refs/heads/master.
remote: 
remote: - GITHUB PUSH PROTECTION
remote:   —————————————————————————————————————————
remote:     Resolve the following violations before pushing again
remote: 
remote:     - Push cannot contain secrets
remote: 
remote:     
remote:      (?) Learn how to resolve a blocked push
remote:      https://docs.github.com/code-security/secret-scanning/working-with-secret-scanning-and-push-protection/working-with-push-protection-from-the-command-line#resolving-a-blocked-push
remote:     
remote:     
remote:       —— GitHub Personal Access Token ——————————————————————
remote:        locations:
remote:          - commit: 3dbefd07df45839aa845f4053ff6222de4a836ba
remote:            path: README.md:2
remote:     
remote:        (?) To push, remove secret from commit(s) or follow this URL to allow the secret.
remote:        https://github.com/MichelsonIU815/lab05/security/secret-scanning/unblock-secret/2ugMFxXXTUeMFGgLHTdNOxRPzWP
remote:     
remote: 
remote: 
To https://github.com/MichelsonIU815/lab05
 ! [remote rejected] master -> master (push declined due to repository rule violations)
error: не удалось отправить некоторые ссылки в «https://github.com/MichelsonIU815/lab05»
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ ^C
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab05$ git push origin master
Username for 'https://github.com': MichelsonIU815
Password for 'https://MichelsonIU815@github.com': 
Перечисление объектов: 49, готово.
Подсчет объектов: 100% (49/49), готово.
При сжатии изменений используется до 12 потоков
Сжатие объектов: 100% (31/31), готово.
Запись объектов: 100% (49/49), 11.79 КиБ | 5.90 МиБ/с, готово.
Всего 49 (изменений 14), повторно использовано 36 (изменений 10), повторно использовано пакетов 0
remote: Resolving deltas: 100% (14/14), done.
remote: 
remote: Create a pull request for 'master' on GitHub by visiting:
remote:      https://github.com/MichelsonIU815/lab05/pull/new/master
remote: 
To https://github.com/MichelsonIU815/lab05
 * [new branch]      master -> master
