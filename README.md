michel@MichelUbuntu:~$ export GITHUB_USERNAME=MichelsonIU815
michel@MichelUbuntu:~$ export GITHUB_EMAIL=dmtmikel@mail.ru
michel@MichelUbuntu:~$ alias edit=nano
michel@MichelUbuntu:~$  alias gsed=sed 
michel@MichelUbuntu:~$ cd ${GITHUB_USERNAME}/workspace
michel@MichelUbuntu:~/MichelsonIU815/workspace$ pushd .
~/MichelsonIU815/workspace ~/MichelsonIU815/workspace
michel@MichelUbuntu:~/MichelsonIU815/workspace$ source scripts/activate
michel@MichelUbuntu:~/MichelsonIU815/workspace$ git clone https://github.com/${GITHUB_USERNAME}/lab05 projects/lab06
Клонирование в «projects/lab06»...
remote: Enumerating objects: 52, done.
remote: Counting objects: 100% (52/52), done.
remote: Compressing objects: 100% (30/30), done.
remote: Total 52 (delta 15), reused 48 (delta 14), pack-reused 0 (from 0)
Получение объектов: 100% (52/52), 17.08 КиБ | 672.00 КиБ/с, готово.
Определение изменений: 100% (15/15), готово.
michel@MichelUbuntu:~/MichelsonIU815/workspace$ cd projects/lab06
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ git remote remove origin
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab06
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ gsed -i '/project(print)/a\
> set(PRINT_VERSION_STRING "v\${PRINT_VERSION}")
> ' CMakeLists.txt
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ gsed -i '/project(print)/a\
> set(PRINT_VERSION\
>   \${PRINT_VERSION_MAJOR}.\${PRINT_VERSION_MINOR}.\${PRINT_VERSION_PATCH}.\${PRINT_VERSION_TWEAK})
> ' CMakeLists.txt
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ gsed -i '/project(print)/a\
> set(PRINT_VERSION_TWEAK 0)
> ' CMakeLists.txt
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ gsed -i '/project(print)/a\
> set(PRINT_VERSION_PATCH 0)
> ' CMakeLists.txt
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ gsed -i '/project(print)/a\
> set(PRINT_VERSION_MINOR 1)
> ' CMakeLists.txt
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ gsed -i '/project(print)/a\
> set(PRINT_VERSION_MAJOR 0)
> ' CMakeLists.txt
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ git diff
diff --git a/CMakeLists.txt b/CMakeLists.txt
index 89739e7..7497219 100644
--- a/CMakeLists.txt
+++ b/CMakeLists.txt
@@ -7,6 +7,13 @@ option(BUILD_EXAMPLES "Build examples" OFF)
 option(BUILD_TESTS "Build tests" OFF)
 
 project(print)
+set(PRINT_VERSION_MAJOR 0)
+set(PRINT_VERSION_MINOR 1)
+set(PRINT_VERSION_PATCH 0)
+set(PRINT_VERSION_TWEAK 0)
+set(PRINT_VERSION
+  ${PRINT_VERSION_MAJOR}.${PRINT_VERSION_MINOR}.${PRINT_VERSION_PATCH}.${PRINT_VERSION_TWEAK})
+set(PRINT_VERSION_STRING "v${PRINT_VERSION}")
 
 add_library(print STATIC ${CMAKE_CURRENT_SOURCE_DIR}/sources/print.cpp)
 
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ touch DESCRIPTION && edit DESCRIPTION
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ touch ChangeLog.md
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ export DATE="`LANG=en_US date +'%a %b %d %Y'`"
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ cat > ChangeLog.md <<EOF
> * ${DATE} ${GITHUB_USERNAME} <${GITHUB_EMAIL}> 0.1.0.0
> - Initial RPM release
> EOF
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ cat > CPackConfig.cmake <<EOF
> include(InstallRequiredSystemLibraries)
> EOF
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ cat >> CPackConfig.cmake <<EOF
> set(CPACK_PACKAGE_CONTACT ${GITHUB_EMAIL})
set(CPACK_PACKAGE_VERSION_MAJOR \${PRINT_VERSION_MAJOR})
set(CPACK_PACKAGE_VERSION_MINOR \${PRINT_VERSION_MINOR})
set(CPACK_PACKAGE_VERSION_PATCH \${PRINT_VERSION_PATCH})
set(CPACK_PACKAGE_VERSION_TWEAK \${PRINT_VERSION_TWEAK})
set(CPACK_PACKAGE_VERSION \${PRINT_VERSION})
set(CPACK_PACKAGE_DESCRIPTION_FILE \${CMAKE_CURRENT_SOURCE_DIR}/DESCRIPTION)
set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "static C++ library for printing")
> EOF
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ cat >> CPackConfig.cmake <<EOF
> set(CPACK_RESOURCE_FILE_LICENSE \${CMAKE_CURRENT_SOURCE_DIR}/LICENSE)
set(CPACK_RESOURCE_FILE_README \${CMAKE_CURRENT_SOURCE_DIR}/README.md)
> EOF
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ cat >> CPackConfig.cmake <<EOF
> set(CPACK_RPM_PACKAGE_NAME "print-devel")
set(CPACK_RPM_PACKAGE_LICENSE "MIT")
set(CPACK_RPM_PACKAGE_GROUP "print")
set(CPACK_RPM_CHANGELOG_FILE \${CMAKE_CURRENT_SOURCE_DIR}/ChangeLog.md)
set(CPACK_RPM_PACKAGE_RELEASE 1)
> EOF
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$  cat >> CPackConfig.cmake <<EOF
> 
set(CPACK_DEBIAN_PACKAGE_NAME "libprint-dev")
set(CPACK_DEBIAN_PACKAGE_PREDEPENDS "cmake >= 3.0")
set(CPACK_DEBIAN_PACKAGE_RELEASE 1)
> EOF
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ cat >> CPackConfig.cmake <<EOF
> include(CPack)
> EOF
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ cat >> CMakeLists.txt <<EOF
> include(CPackConfig.cmake)
> EOF
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ gsed -i 's/lab05/lab06/g' README.md
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ git add .
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ git commit -m"added cpack config"
[master fe1ac66] added cpack config
 5 files changed, 77 insertions(+), 46 deletions(-)
 create mode 100644 CPackConfig.cmake
 create mode 100644 ChangeLog.md
 create mode 100644 DESCRIPTION
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ git tag v0.1.0.0
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$  git push origin master --tags
Username for 'https://github.com': MichelsonIU815     
Password for 'https://MichelsonIU815@github.com': 
Перечисление объектов: 58, готово.
Подсчет объектов: 100% (58/58), готово.
При сжатии изменений используется до 12 потоков
Сжатие объектов: 100% (35/35), готово.
Запись объектов: 100% (58/58), 18.25 КиБ | 6.08 МиБ/с, готово.
Всего 58 (изменений 18), повторно использовано 49 (изменений 15), повторно использовано пакетов 0
remote: Resolving deltas: 100% (18/18), done.
remote: error: GH013: Repository rule violations found for refs/tags/v0.1.0.0.
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
remote:        https://github.com/MichelsonIU815/lab06/security/secret-scanning/unblock-secret/2ugS4G2NtoUnRkWd6eW7QI85vCr
remote:     
remote: 
remote: 
To https://github.com/MichelsonIU815/lab06
 ! [rejected]        master -> master (fetch first)
 ! [remote rejected] v0.1.0.0 -> v0.1.0.0 (push declined due to repository rule violations)
error: не удалось отправить некоторые ссылки в «https://github.com/MichelsonIU815/lab06»
подсказка: Updates were rejected because the remote contains work that you do not
подсказка: have locally. This is usually caused by another repository pushing to
подсказка: the same ref. If you want to integrate the remote changes, use
подсказка: 'git pull' before pushing again.
подсказка: See the 'Note about fast-forwards' in 'git push --help' for details.
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$  git push origin master --tags
Username for 'https://github.com': MichelsonIU815
Password for 'https://MichelsonIU815@github.com': 
Перечисление объектов: 58, готово.
Подсчет объектов: 100% (58/58), готово.
При сжатии изменений используется до 12 потоков
Сжатие объектов: 100% (35/35), готово.
Запись объектов: 100% (58/58), 18.25 КиБ | 6.08 МиБ/с, готово.
Всего 58 (изменений 18), повторно использовано 49 (изменений 15), повторно использовано пакетов 0
remote: Resolving deltas: 100% (18/18), done.
To https://github.com/MichelsonIU815/lab06
 * [new tag]         v0.1.0.0 -> v0.1.0.0
 ! [rejected]        master -> master (fetch first)
error: не удалось отправить некоторые ссылки в «https://github.com/MichelsonIU815/lab06»
подсказка: Updates were rejected because the remote contains work that you do not
подсказка: have locally. This is usually caused by another repository pushing to
подсказка: the same ref. If you want to integrate the remote changes, use
подсказка: 'git pull' before pushing again.
подсказка: See the 'Note about fast-forwards' in 'git push --help' for details.
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ git pull
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Распаковка объектов: 100% (3/3), 4.68 КиБ | 2.34 МиБ/с, готово.
Из https://github.com/MichelsonIU815/lab06
 * [новая ветка]     master     -> origin/master
У текущей ветки нет информации об отслеживании.
Пожалуйста, укажите с какой веткой вы хотите слить изменения.
Для дополнительной информации, смотрите git-pull(1).

    git pull <внешний-репозиторий> <ветка>

Если вы хотите указать информацию о отслеживаемой ветке, выполните:

    git branch --set-upstream-to=origin/<ветка> master

michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$  git push origin master --tags
Username for 'https://github.com': MichelsonIU815
Password for 'https://MichelsonIU815@github.com': 
To https://github.com/MichelsonIU815/lab06
 ! [rejected]        master -> master (non-fast-forward)
error: не удалось отправить некоторые ссылки в «https://github.com/MichelsonIU815/lab06»
подсказка: Updates were rejected because the tip of your current branch is behind
подсказка: its remote counterpart. If you want to integrate the remote changes,
подсказка: use 'git pull' before pushing again.
подсказка: See the 'Note about fast-forwards' in 'git push --help' for details.
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ git push --force
Username for 'https://github.com': MichelsonIU815
Password for 'https://MichelsonIU815@github.com': 
Всего 0 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
To https://github.com/MichelsonIU815/lab06
 + e9cfb9e...fe1ac66 master -> master (forced update)
branch 'master' set up to track 'origin/master'.
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ cmake -H. -B_build
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
-- Configuring done (0.3s)
-- Generating done (0.0s)
-- Build files have been written to: /home/michel/MichelsonIU815/workspace/projects/lab06/_build
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ cmake --build _build
[ 50%] Building CXX object CMakeFiles/print.dir/sources/print.cpp.o
[100%] Linking CXX static library libprint.a
[100%] Built target print
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ cd _build
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06/_build$ cpack -G "TGZ"
CPack: Create package using TGZ
CPack: Install projects
CPack: - Run preinstall target for: print
CPack: - Install project: print []
CPack: Create package
CPack: - package: /home/michel/MichelsonIU815/workspace/projects/lab06/_build/print-0.1.0.0-Linux.tar.gz generated.
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06/_build$ cd ..
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ cmake -H. -B_build -DCPACK_GENERATOR="TGZ"
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- Configuring done (0.0s)
-- Generating done (0.0s)
-- Build files have been written to: /home/michel/MichelsonIU815/workspace/projects/lab06/_build
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ cmake --build _build --target package
[100%] Built target print
Run CPack packaging tool...
CPack: Create package using TGZ
CPack: Install projects
CPack: - Run preinstall target for: print
CPack: - Install project: print []
CPack: Create package
CPack: - package: /home/michel/MichelsonIU815/workspace/projects/lab06/_build/print-0.1.0.0-Linux.tar.gz generated.
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ mkdir artifacts
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ mv _build/*.tar.gz artifacts
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ tree artifacts
artifacts
└── print-0.1.0.0-Linux.tar.gz

1 directory, 1 file
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab06$ 
