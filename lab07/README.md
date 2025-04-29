luka@luka-VirtualBox:~$ export GITHUB_USERNAME=Joker762-rgb
luka@luka-VirtualBox:~$ alias gsed=sed
luka@luka-VirtualBox:~$ cd ${GITHUB_USERNAME}/workspace
luka@luka-VirtualBox:~/Joker762-rgb/workspace$ pushd .
~/Joker762-rgb/workspace ~/Joker762-rgb/workspace
luka@luka-VirtualBox:~/Joker762-rgb/workspace$ source scripts/activate
luka@luka-VirtualBox:~/Joker762-rgb/workspace$ git clone https://github.com/${GITHUB_USERNAME}/lab06 projects/lab07
Клонирование в «projects/lab07»...
remote: Enumerating objects: 220, done.
remote: Counting objects: 100% (220/220), done.
remote: Compressing objects: 100% (113/113), done.
remote: Total 220 (delta 82), reused 213 (delta 80), pack-reused 0 (from 0)
Получение объектов: 100% (220/220), 1.01 МиБ | 237.00 КиБ/с, готово.
Определение изменений: 100% (82/82), готово.
luka@luka-VirtualBox:~/Joker762-rgb/workspace$ cd projects/lab07
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git remote remove origin
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab07
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git pull origin master
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Распаковка объектов: 100% (4/4), 1.49 КиБ | 1.49 МиБ/с, готово.
Из https://github.com/Joker762-rgb/lab07
 * branch            master     -> FETCH_HEAD
 * [новая ветка]     master     -> origin/master
подсказка: You have divergent branches and need to specify how to reconcile them.
подсказка: You can do so by running one of the following commands sometime before
подсказка: your next pull:
подсказка: 
подсказка:   git config pull.rebase false  # merge
подсказка:   git config pull.rebase true   # rebase
подсказка:   git config pull.ff only       # fast-forward only
подсказка: 
подсказка: You can replace "git config" with "git config --global" to set a default
подсказка: preference for all repositories. You can also pass --rebase, --no-rebase,
подсказка: or --ff-only on the command line to override the configured default per
подсказка: invocation.
fatal: Need to specify how to reconcile divergent branches.
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git config pull.rebase false
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git pull origin master --no-rebase
Из https://github.com/Joker762-rgb/lab07
 * branch            master     -> FETCH_HEAD
fatal: отказ слияния несвязанных историй изменений
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git pull origin master --allow-unrelated-histories
Из https://github.com/Joker762-rgb/lab07
 * branch            master     -> FETCH_HEAD
Автослияние LICENSE
КОНФЛИКТ (добавление/добавление): Конфликт слияния в LICENSE
Автослияние README.md
КОНФЛИКТ (добавление/добавление): Конфликт слияния в README.md
Сбой автоматического слияния; исправьте конфликты, затем зафиксируйте результат.
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git add README.md
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git pull origin master --allow-unrelated-histories
error: Невозможно выполнить получение, так как у вас имеются не слитые файлы.
подсказка: Исправьте их в рабочем каталоге, затем запустите «git add/rm <файл>»,
подсказка: чтобы пометить исправление и сделайте коммит.
fatal: Выход из-за неразрешенного конфликта.
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git commit
U	LICENSE
error: Невозможно закоммитить, так как у вас имеются не слитые файлы.
подсказка: Исправьте их в рабочем каталоге, затем запустите «git add/rm <файл>»,
подсказка: чтобы пометить исправление и сделайте коммит.
fatal: Выход из-за неразрешенного конфликта.
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git add README.md
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git commit
U	LICENSE
error: Невозможно закоммитить, так как у вас имеются не слитые файлы.
подсказка: Исправьте их в рабочем каталоге, затем запустите «git add/rm <файл>»,
подсказка: чтобы пометить исправление и сделайте коммит.
fatal: Выход из-за неразрешенного конфликта.
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git status
Текущая ветка: master
У вас есть не слитые пути.
  (разрешите конфликты, затем запустите «git commit»)
  (используйте «git merge --abort», чтобы остановить операцию слияния)

Изменения, которые будут включены в коммит:
	изменено:      README.md

Не слитые пути:
  (используйте «git add <файл>...», чтобы пометить разрешение конфликта)
	оба добавлены:  LICENSE

luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git add LICENSE
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git commit -m "Объединение LICENSE после конфликта"
[master 5c26ec6] Объединение LICENSE после конфликта
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git status
Текущая ветка: master
нечего коммитить, нет изменений в рабочем каталоге
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git pull origin master
Из https://github.com/Joker762-rgb/lab07
 * branch            master     -> FETCH_HEAD
Уже актуально.
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ mkdir -p cmake
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ wget https://raw.githubusercontent.com/cpp-pm/gate/master/cmake/HunterGate.cmake -O cmake/HunterGate.cmake
--2025-04-18 18:57:47--  https://raw.githubusercontent.com/cpp-pm/gate/master/cmake/HunterGate.cmake
Распознаётся raw.githubusercontent.com (raw.githubusercontent.com)… 185.199.108.133, 185.199.111.133, 185.199.110.133, ...
Подключение к raw.githubusercontent.com (raw.githubusercontent.com)|185.199.108.133|:443... соединение установлено.
HTTP-запрос отправлен. Ожидание ответа… 200 OK
Длина: 17231 (17K) [text/plain]
Сохранение в: ‘cmake/HunterGate.cmake’

cmake/HunterGate.cmake        100%[=================================================>]  16,83K  --.-KB/s    за 0,05s   

2025-04-18 18:57:48 (335 KB/s) - ‘cmake/HunterGate.cmake’ сохранён [17231/17231]

luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ gsed -i '/cmake_minimum_required(VERSION 3.4)/a\
> include("cmake/HunterGate.cmake")

HunterGate(
    URL "https://github.com/cpp-pm/hunter/archive/v0.23.308.tar.gz"
    SHA1 "23f1b5a0acffae50fda423388c843a8e7b6e1eb0"
)' CMakeLists.txt
sed: -e выражение #1, символ 77: лишние символы после команды
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ gsed -i '/cmake_minimum_required(VERSION 3.4)/a \
> include("cmake/HunterGate.cmake") \
HunterGate( \
    URL "https://github.com/cpp-pm/hunter/archive/v0.23.308.tar.gz" \
    SHA1 "23f1b5a0acffae50fdad2338bc843a8e7b6e1ebb" \
)' CMakeLists.txt
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git rm -rf third-party/gtest
rm 'third-party/gtest'
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ gsed -i '/set(PRINT_VERSION_STRING "v\${PRINT_VERSION}")/a\
> hunter_add_package(GTest)
find_package(GTest CONFIG REQUIRED)' CMakeLists.txt
sed: -e выражение #1, символ 78: неизвестная команда: `f'
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ gsed -i '/set(PRINT_VERSION_STRING "v\${PRINT_VERSION}")/a \
> hunter_add_package(GTest)
find_package(GTest CONFIG REQUIRED)' CMakeLists.txt
sed: -e выражение #1, символ 79: неизвестная команда: `f'
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ gsed -i '/set(PRINT_VERSION_STRING "v${PRINT_VERSION}")/a \
> hunter_add_package(GTest)\
find_package(GTest CONFIG REQUIRED)' CMakeLists.txt
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ gsed -i 's/add_subdirectory(third-party\/gtest)//' CMakeLists.txt
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ gsed -i 's/gtest_main/GTest::main/' CMakeLists.txt
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ cmake -H. -B_builds -DBUILD_TESTS=ON
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.



[hunter ** INTERNAL **] Short SHA1 collision:
[hunter ** INTERNAL **]   23f1b5a0acffae50fda423388c843a8e7b6e1eb0 (from /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/SHA1)
[hunter ** INTERNAL **]   23f1b5a0acffae50fdad2338bc843a8e7b6e1ebb (HunterGate)
[hunter ** INTERNAL **] [Directory:/home/luka/Joker762-rgb/workspace/projects/lab07]

------------------------------ ERROR ------------------------------
    https://hunter.readthedocs.io/en/latest/reference/errors/error.internal.html
-------------------------------------------------------------------

CMake Error at cmake/HunterGate.cmake:88 (message):
Call Stack (most recent call first):
  cmake/HunterGate.cmake:98 (hunter_gate_error_page)
  cmake/HunterGate.cmake:526 (hunter_gate_internal_error)
  CMakeLists.txt:3 (HunterGate)


-- Configuring incomplete, errors occurred!
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ cmake -H. -B_builds -DBUILD_TESTS=ON
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:9 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:9 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_set_config_location.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:13 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_private_data.cmake:12 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:35 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_initialize.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:36 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


-- The C compiler identification is GNU 13.3.0
-- The CXX compiler identification is GNU 13.3.0
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
-- [hunter] Calculating Toolchain-SHA1
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- [hunter] Calculating Config-SHA1
-- [hunter] HUNTER_ROOT: /home/luka/.hunter
-- [hunter] [ Hunter-ID: 23f1b5a | Toolchain-ID: fb15dbb | Config-ID: bf2be25 ]
CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:9 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:9 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_set_config_location.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:13 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:9 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:9 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_set_config_location.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:13 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_save_to_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:26 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_save_to_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:26 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_save_to_cache.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:26 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_save_to_cache.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:26 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_save_to_cache.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:26 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


-- [hunter] GTEST_ROOT: /home/luka/.hunter/_Base/23f1b5a/fb15dbb/bf2be25/Install (ver.: 1.11.0)
-- Found GTest: /home/luka/.hunter/_Base/23f1b5a/fb15dbb/bf2be25/Install/lib/cmake/GTest/GTestConfig.cmake (found version "1.11.0")  
-- Configuring done (0.9s)
CMake Error at CMakeLists.txt:64 (add_executable):
  Cannot find source file:

    /home/luka/Joker762-rgb/workspace/projects/lab07/demo/main.cpp

  Tried extensions .c .C .c++ .cc .cpp .cxx .cu .mpp .m .M .mm .ixx .cppm
  .ccm .cxxm .c++m .h .hh .h++ .hm .hpp .hxx .in .txx .f .F .for .f77 .f90
  .f95 .f03 .hip .ispc


CMake Error at CMakeLists.txt:64 (add_executable):
  No SOURCES given to target: demo


CMake Generate step failed.  Build files cannot be regenerated correctly.
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ mkdir -p demo
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ touch demo/main.cpp
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ cmake -H. -B_builds -DBUILD_TESTS=ON
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:9 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:9 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_set_config_location.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:13 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_private_data.cmake:12 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:35 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_initialize.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/Hunter:36 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


-- [hunter] Calculating Toolchain-SHA1
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- [hunter] Calculating Config-SHA1
-- [hunter] HUNTER_ROOT: /home/luka/.hunter
-- [hunter] [ Hunter-ID: 23f1b5a | Toolchain-ID: fb15dbb | Config-ID: bf2be25 ]
CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:9 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:9 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_set_config_location.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:13 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:9 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:9 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_set_config_location.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_apply_gate_settings.cmake:13 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_finalize.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_load_from_cache.cmake:6 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:22 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_save_to_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:26 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_save_to_cache.cmake:4 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:26 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_save_to_cache.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:26 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_save_to_cache.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:26 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


CMake Deprecation Warning at /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_save_to_cache.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_download.cmake:26 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/luka/.hunter/_Base/Download/Hunter/0.23.308/23f1b5a/Unpacked/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:24 (hunter_add_package)


-- [hunter] GTEST_ROOT: /home/luka/.hunter/_Base/23f1b5a/fb15dbb/bf2be25/Install (ver.: 1.11.0)
-- Configuring done (0.6s)
-- Generating done (0.0s)
-- Build files have been written to: /home/luka/Joker762-rgb/workspace/projects/lab07/_builds
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ cmake --build _builds
[ 16%] Building CXX object CMakeFiles/print.dir/sources/print.cpp.o
[ 33%] Linking CXX static library libprint.a
[ 33%] Built target print
[ 50%] Building CXX object CMakeFiles/check.dir/tests/test1.cpp.o
[ 66%] Linking CXX executable check
[ 66%] Built target check
[ 83%] Building CXX object CMakeFiles/demo.dir/demo/main.cpp.o
[100%] Linking CXX executable demo
[100%] Built target demo
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ cmake --build _builds --target test
Running tests...
Test project /home/luka/Joker762-rgb/workspace/projects/lab07/_builds
    Start 1: check
1/1 Test #1: check ............................   Passed    0.00 sec

100% tests passed, 0 tests failed out of 1

Total Test time (real) =   0.00 sec
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ ls -la $HOME/.hunter
итого 12
drwxrwxr-x  3 luka luka 4096 апр 17 22:47 .
drwxr-x--- 20 luka luka 4096 апр 18 18:27 ..
drwxrwxr-x  6 luka luka 4096 апр 18 18:18 _Base
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git clone https://github.com/cpp-pm/hunter $HOME/projects/hunter
fatal: целевой путь «/home/luka/projects/hunter» уже существует и не является пустым каталогом.
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ export HUNTER_ROOT=$HOME/projects/hunter
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ rm -rf _builds
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ cmake -H. -B_builds -DBUILD_TESTS=ON
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- The C compiler identification is GNU 13.3.0
-- The CXX compiler identification is GNU 13.3.0
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
-- [hunter] Calculating Toolchain-SHA1
-- [hunter] Calculating Config-SHA1
-- [hunter] HUNTER_ROOT: /home/luka/projects/hunter
-- [hunter] [ Hunter-ID: xxxxxxx | Toolchain-ID: fb15dbb | Config-ID: d14f46d ]
-- [hunter] GTEST_ROOT: /home/luka/projects/hunter/_Base/xxxxxxx/fb15dbb/d14f46d/Install (ver.: 1.15.2)
-- Found GTest: /home/luka/projects/hunter/_Base/xxxxxxx/fb15dbb/d14f46d/Install/lib/cmake/GTest/GTestConfig.cmake (found version "1.15.2")  
-- Configuring done (0.9s)
-- Generating done (0.0s)
-- Build files have been written to: /home/luka/Joker762-rgb/workspace/projects/lab07/_builds
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ cmake --build _builds
[ 16%] Building CXX object CMakeFiles/print.dir/sources/print.cpp.o
[ 33%] Linking CXX static library libprint.a
[ 33%] Built target print
[ 50%] Building CXX object CMakeFiles/check.dir/tests/test1.cpp.o
[ 66%] Linking CXX executable check
[ 66%] Built target check
[ 83%] Building CXX object CMakeFiles/demo.dir/demo/main.cpp.o
[100%] Linking CXX executable demo
[100%] Built target demo
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ cmake --build _builds --target test
Running tests...
Test project /home/luka/Joker762-rgb/workspace/projects/lab07/_builds
    Start 1: check
1/1 Test #1: check ............................   Passed    0.00 sec

100% tests passed, 0 tests failed out of 1

Total Test time (real) =   0.00 sec
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ cat $HUNTER_ROOT/cmake/configs/default.cmake
# Copyright (c) 2013-2020, Ruslan Baratov, Rahul Sheth
# All rights reserved.

# Do not place header guards here

# Set CMake variables:
#   * HUNTER_${PACKAGE_NAME}_VERSION

# Usage:
#   hunter_default_version(Foo VERSION 1.0.0)
#   hunter_default_version(Boo VERSION 1.2.3z)

include(hunter_default_version)
include(hunter_user_error)

# NOTE: no names with spaces!

hunter_default_version(ARM_NEON_2_x86_SSE VERSION 1.0.0-p0)
hunter_default_version(AllTheFlopsThreads VERSION 0.1-p0)
hunter_default_version(Alut VERSION 1.1.0-469287b-p0)
hunter_default_version(Android-Apk VERSION 1.1.14)
hunter_default_version(Android-Build-Tools VERSION 27.0.3)
hunter_default_version(Android-Google-Repository VERSION 58)
hunter_default_version(Android-Modules VERSION 1.0.0)
hunter_default_version(Android-SDK VERSION 0.0.6)
hunter_default_version(Android-SDK-Platform-tools VERSION r28.0.0)
hunter_default_version(Android-SDK-Tools VERSION 25.2.5)
hunter_default_version(Android-Support-Repository VERSION 47)
hunter_default_version(AngelScript VERSION 2.30-p0)
hunter_default_version(ArrayFire VERSION 3.3.1-p0)
hunter_default_version(Assimp VERSION 5.2.5-9519a62)
hunter_default_version(Async++ VERSION 0.0.3-hunter)
hunter_default_version(Avahi VERSION 0.6.31)
hunter_default_version(BZip2 VERSION 1.0.8-p0)
hunter_default_version(Beast VERSION 1.0.0-b84-hunter-0)

if(MINGW)
  # https://github.com/boostorg/build/issues/301
  hunter_default_version(Boost VERSION 1.64.0)
else()
  hunter_default_version(Boost VERSION 1.83.0)
endif()

hunter_default_version(BoostCompute VERSION 0.5-p0)
hunter_default_version(BoostProcess VERSION 0.5)
hunter_default_version(BoringSSL VERSION 0.0.0-0f5ecd3a8-p0)
hunter_default_version(Box2D VERSION 2.3.1-p0)
hunter_default_version(CLAPACK VERSION 3.2.1)
hunter_default_version(CLI11 VERSION 2.3.2)
hunter_default_version(CURL VERSION 8.5.0-p0)
hunter_default_version(CapnProto VERSION 0.7.0)
hunter_default_version(Catch VERSION 2.13.9)
hunter_default_version(Clang VERSION 6.0.1-p0)
hunter_default_version(ClangToolsExtra VERSION 6.0.1) # Clang
hunter_default_version(Comet VERSION 4.0.2)
hunter_default_version(CppNetlib VERSION 0.10.1-hunter-3)
hunter_default_version(CppNetlibUri VERSION 1.0.5-hunter)
hunter_default_version(CreateLaunchers VERSION 0.2.1)
hunter_default_version(CsvParserCPlusPlus VERSION 1.0.1)
hunter_default_version(EGL-Registry VERSION 0.0.0-dc0b58d-p0)
hunter_default_version(Eigen VERSION 3.4.0)
hunter_default_version(Expat VERSION 2.2.9-p0)
hunter_default_version(FLAC VERSION 1.3.4-p0)
hunter_default_version(FP16 VERSION 0.0.0-febbb1c-p0)
hunter_default_version(FakeIt VERSION 2.0.3)
hunter_default_version(Fruit VERSION 3.1.1-p0)
hunter_default_version(FunctionalPlus VERSION 0.2-p0)
hunter_default_version(GPUImage VERSION 0.1.6-p9)
hunter_default_version(GSL VERSION 2.1.0-p2)

if(MSVC80)
  hunter_default_version(GTest VERSION 1.7.0-hunter-6)
else()
  hunter_default_version(GTest VERSION 1.15.2)
endif()

hunter_default_version(HalideIR VERSION 0.0-32057b5-p0)
hunter_default_version(HastyNoise VERSION 0.8.3)
hunter_default_version(ICU VERSION 63.1-p5)
hunter_default_version(IF97 VERSION 2.1.2)
hunter_default_version(Igloo VERSION 1.1.1-hunter)
hunter_default_version(IlmBase VERSION 2.5.1-p0)
hunter_default_version(Imath VERSION 3.1.5)
hunter_default_version(Immer VERSION 0.6.2-cf44615)
hunter_default_version(Jpeg VERSION 9e-p0)
hunter_default_version(JsonSpirit VERSION 0.0.4-hunter)
hunter_default_version(KTX-Software VERSION 4.0.0-efc9f09-p0)
hunter_default_version(KhronosDataFormat VERSION 1.3.1-1f8c852-p3)
hunter_default_version(LAPACK VERSION 3.7.1)
hunter_default_version(LLVM VERSION 13.0.1) # Clang
hunter_default_version(LLVMCompilerRT VERSION 6.0.1) # Clang
hunter_default_version(Lager VERSION 0.0.0-dbc1fde-p0)
hunter_default_version(Leathers VERSION 0.1.8)
hunter_default_version(Leptonica VERSION 1.74.2-p4)
hunter_default_version(LibCDS VERSION 2.3.1)
hunter_default_version(Libcxx VERSION 3.6.2) # Clang
hunter_default_version(Libcxxabi VERSION 3.6.2) # Clang
hunter_default_version(Libevent VERSION 2.1.8-p4)
hunter_default_version(Libssh2 VERSION 1.9.0-p0)
hunter_default_version(LodePNG VERSION 0.0.0-p1)
hunter_default_version(Lua VERSION 5.3.5)
hunter_default_version(MathFu VERSION 1.1.0-p0)
hunter_default_version(Microsoft.GSL VERSION 2.0.0-p0)
hunter_default_version(MySQL-client VERSION 6.1.9-p1)
hunter_default_version(NASM VERSION 2.15.02)
hunter_default_version(NLopt VERSION 2.5.0-p0)
hunter_default_version(ONNX VERSION 1.4.1-p0)
hunter_default_version(OpenAL VERSION 1.23.1)
hunter_default_version(OpenBLAS VERSION 0.3.27)
hunter_default_version(OpenCL VERSION 2022.01.04-p1)
hunter_default_version(OpenCL-Headers VERSION 2022.01.04)
hunter_default_version(OpenCL-cpp VERSION 2.0.16-61a5c9a-p0)
if(MSVC)
  hunter_default_version(OpenCV VERSION 4.10.0-p0)
  hunter_default_version(OpenCV-Extra VERSION 4.10.0)
else()
  # 4.10.0 has a build problem with TIFF header defines
  hunter_default_version(OpenCV VERSION 4.8.1-p0)
  hunter_default_version(OpenCV-Extra VERSION 4.8.1)
endif()
hunter_default_version(OpenEXR VERSION 3.1.5-p0)
hunter_default_version(OpenGL-Registry VERSION 0.0.0-d15191e-p0)
hunter_default_version(OpenNMTTokenizer VERSION 1.11.0-p1)
hunter_default_version(OpenSSL VERSION 3.0.12)
hunter_default_version(OpenSceneGraph VERSION 3.6.3-p0)
hunter_default_version(Opus VERSION 1.3.1)
hunter_default_version(PNG VERSION 1.6.26-p6)
hunter_default_version(PROJ4 VERSION 5.0.0)
hunter_default_version(PhysUnits VERSION 1.1.0-p0)
hunter_default_version(PocoCpp VERSION 1.10.1-p0)
hunter_default_version(PostgreSQL VERSION 10.0.0)
hunter_default_version(Protobuf VERSION 3.19.4-p0)

string(COMPARE EQUAL "${CMAKE_SYSTEM_NAME}" "Linux" _is_linux)
if(_is_linux OR MINGW)
  # qt-qml example is broken on Linux
  # qt-core example is broken on MinGW
  hunter_default_version(Qt VERSION 5.5.1-cvpixelbuffer-2-p9)
elseif(IOS OR ANDROID)
  hunter_default_version(Qt VERSION 5.9.1-p0)
else()
  hunter_default_version(Qt VERSION 5.11.3)
endif()

hunter_default_version(QtAndroidCMake VERSION 1.0.9)
hunter_default_version(QtCMakeExtra VERSION 1.0.34)
hunter_default_version(QtPropertyEditor VERSION 2.1.3-p0)
hunter_default_version(QtQmlManager VERSION 1.0.0)
hunter_default_version(Qwt VERSION 6.1-p3)
hunter_default_version(RapidJSON VERSION 1.1.0-b557259-p0)
hunter_default_version(RapidXML VERSION 1.13)
hunter_default_version(RedisClient VERSION 0.6.1-p1)
hunter_default_version(SDL2 VERSION 2.30.2)
hunter_default_version(SDL_image VERSION 2.0.5-p0)
hunter_default_version(SDL_mixer VERSION 2.0.4-p0)
hunter_default_version(SDL_net VERSION 2.2.0-p0)
hunter_default_version(SDL_ttf VERSION 2.0.18-p0)
hunter_default_version(SFML VERSION 2.5.1-p0)
hunter_default_version(SPIRV-Headers VERSION 1.5.4.raytracing.fixed)
hunter_default_version(SPIRV-Tools VERSION 2020.4-p0)
hunter_default_version(SimpleSignal VERSION 0.0.0-79c3f68-p1)
hunter_default_version(Snappy VERSION 1.1.7)
hunter_default_version(Sober VERSION 0.1.3)
hunter_default_version(Sqlpp11 VERSION 0.57-p0)
hunter_default_version(SuiteSparse VERSION 7.5.1-1)
hunter_default_version(TCLAP VERSION 1.2.2-p1)
hunter_default_version(TIFF VERSION 4.0.2-p5)
hunter_default_version(Tesseract VERSION 3.05.01-hunter-3)
hunter_default_version(Urho3D VERSION 1.7-p15)
hunter_default_version(Vulkan-Headers VERSION 1.2.182-p0)
hunter_default_version(VulkanMemoryAllocator VERSION 2.3.0-p0)
hunter_default_version(WDC VERSION 1.1.5)
hunter_default_version(WTL VERSION 9.1.5321)
hunter_default_version(Washer VERSION 0.1.2)
hunter_default_version(WebKit VERSION 0.0.2-p0)
hunter_default_version(WebP VERSION 1.2.4-p0)
hunter_default_version(WinSparkle VERSION 0.4.0)
hunter_default_version(YAJL VERSION 2.1.0-p0)
hunter_default_version(ZLIB VERSION 1.3.0-p0)
hunter_default_version(ZMQPP VERSION 4.2.0-p0)
hunter_default_version(ZeroMQ VERSION 4.2.3-p1)
hunter_default_version(Zug VERSION 0.0.1-be20cae)

hunter_default_version(abseil VERSION 20240116.2)
hunter_default_version(acf VERSION 0.1.14)
hunter_default_version(actionlib VERSION 1.11.13-p0)
hunter_default_version(aes VERSION 0.0.1-p1)
hunter_default_version(aglet VERSION 1.2.2)
hunter_default_version(android_arm64_v8a_system_image_packer VERSION 1.0.0)
hunter_default_version(android_arm_eabi_v7a_system_image_packer VERSION 1.0)
hunter_default_version(android_build_tools_packer VERSION 1.0.0)
hunter_default_version(android_google_apis_intel_x86_atom_system_image_packer VERSION 1.0.0)
hunter_default_version(android_google_apis_packer VERSION 1.0.0)
hunter_default_version(android_google_repository_packer VERSION 1.0.0)
hunter_default_version(android_intel_x86_atom_system_image_packer VERSION 1.0.0)
hunter_default_version(android_mips_system_image_packer VERSION 1.0.0)
hunter_default_version(android_sdk_packer VERSION 1.0.0)
hunter_default_version(android_sdk_platform_packer VERSION 1.0.0)
hunter_default_version(android_sdk_platform_tools_packer VERSION 1.0.0)
hunter_default_version(android_sdk_tools_packer VERSION 1.0.3)
hunter_default_version(android_support_repository_packer VERSION 1.0.0)
hunter_default_version(angles VERSION 1.9.11-p0)
hunter_default_version(apg VERSION 0.0.0-b322f7a-p0)
hunter_default_version(arabica VERSION 0.0.0-a202766-p0)
hunter_default_version(asio VERSION 1.22.1-p1)
hunter_default_version(asio-grpc VERSION 2.6.0)
hunter_default_version(astc-encoder VERSION 3.0-7257cbd-p0)
hunter_default_version(autobahn-cpp VERSION 0.2.0)
hunter_default_version(autoutils VERSION 0.3.0)
hunter_default_version(aws-c-common VERSION 0.5.6)
hunter_default_version(aws-sdk-cpp VERSION 1.9.278-p1)
hunter_default_version(aws_lambda_cpp VERSION v0.2.7-p0)
hunter_default_version(basis_universal VERSION 1.16.3-p0)
hunter_default_version(benchmark VERSION 1.8.3)
hunter_default_version(bento4 VERSION 1.6.0-638-p0)
hunter_default_version(binaryen VERSION 1.38.28-p1)
hunter_default_version(bison VERSION 3.0.4-p0)
hunter_default_version(boost-pba VERSION 1.0.0-p0)
hunter_default_version(botan VERSION 2.11.0-110af9494)
hunter_default_version(breakpad VERSION 0.0.0-12ecff3-p4)
hunter_default_version(brotli VERSION 1.0.9-p0)
hunter_default_version(bullet VERSION 2.87-p0)
hunter_default_version(byte-lite VERSION 0.3.0-p0)
hunter_default_version(c-ares VERSION 1.14.0-p0)
hunter_default_version(caffe VERSION rc3-p2)
hunter_default_version(catkin VERSION 0.7.17-p0)
hunter_default_version(cctz VERSION 2.2.0)
hunter_default_version(ccv VERSION 0.7-p6)
hunter_default_version(cereal VERSION 1.2.2-p0)
if(CMAKE_CXX_COMPILER_ID STREQUAL "GNU" AND CMAKE_CXX_COMPILER_VERSION VERSION_LESS "8.0")
  # Ubuntu 18.04 GCC compiler isn't C++17 conformant enough, stay at lower version
  # - Ubuntu 18.04 disablement: https://github.com/ceres-solver/ceres-solver/commit/40c1a7e18ee040261f87b32374c9a46724ca2214
  # - C++17 requirement: https://github.com/ceres-solver/ceres-solver/commit/1274743609bc59621adc9e311cdeeaad7eb65201
  hunter_default_version(ceres-solver VERSION 2.1.0-p1)
else()
  hunter_default_version(ceres-solver VERSION 2.2.0-p2)
endif()
hunter_default_version(cgltf VERSION 1.10-f9a8804-p0)
hunter_default_version(check_ci_tag VERSION 1.0.0)
hunter_default_version(chromium_zlib VERSION 0.0.0-f87c2b10efb4-p0)
hunter_default_version(civetweb VERSION 1.11-p0)
hunter_default_version(clBLAS VERSION 2.10.0-p0)
hunter_default_version(class_loader VERSION 0.4.1-p0)
hunter_default_version(cmcstl2 VERSION 0.0.0-bee0705e99)
hunter_default_version(complex_bessel VERSION 0.5.0-abab4b5)
hunter_default_version(convertutf VERSION 1.0.1)
hunter_default_version(corrade VERSION 2019.10)
hunter_default_version(cpp-statsd-client VERSION 1.0.1-42f02b4-p0)
hunter_default_version(cpp_redis VERSION 3.5.0-h1)
hunter_default_version(cppast VERSION 0.0.0-b155d6a-p0)
hunter_default_version(cppcodec VERSION 0.2-p0)
hunter_default_version(cppfs VERSION 1.3.0)
hunter_default_version(cpr VERSION 1.3.0)
hunter_default_version(cpuinfo VERSION 0.0.0-d5e37ad-p0)
hunter_default_version(crashpad VERSION v0.0.1-p0)
hunter_default_version(crashup VERSION 0.0.2)
hunter_default_version(crc32c VERSION 1.1.1)
hunter_default_version(cryptopp VERSION 8.2.0-p1)
hunter_default_version(ctti VERSION 0.0.2)
hunter_default_version(cub VERSION 1.8.0-p0)
hunter_default_version(cvmatio VERSION 1.0.28)
hunter_default_version(cvsteer VERSION 0.1.2)
hunter_default_version(cxxopts VERSION 2.2.0)
hunter_default_version(czmq VERSION 4.0.2-p1)
hunter_default_version(damageproto VERSION 1.2.1)
hunter_default_version(date VERSION 3.0.1)
hunter_default_version(dbus VERSION 1.10.0-hunter-4)
hunter_default_version(debug_assert VERSION 1.3.2)
hunter_default_version(dest VERSION 0.8.0-p4)
hunter_default_version(dfdutils VERSION 0.0.0-659a739-p1)
hunter_default_version(dlib VERSION 19.17-p0)
hunter_default_version(dlpack VERSION 0.2-0acb731)
hunter_default_version(dmlc-core VERSION 0.3-3943914-p0)
hunter_default_version(doctest VERSION 2.4.9)
hunter_default_version(double-conversion VERSION 3.1.4)
hunter_default_version(draco VERSION 1.4.1-p0)
hunter_default_version(dri2proto VERSION 2.8)
hunter_default_version(dri3proto VERSION 1.0)
hunter_default_version(drishti VERSION 0.8.9)
hunter_default_version(drishti_assets VERSION 1.8)
hunter_default_version(drishti_faces VERSION 1.2)
hunter_default_version(drm VERSION 2.4.94)
hunter_default_version(duktape VERSION 2.2.1-p0)
hunter_default_version(dynalo VERSION 1.0.3)
hunter_default_version(eigen3-nnls VERSION 1.0.1)
hunter_default_version(enet VERSION 1.3.13-p1)
hunter_default_version(entityx VERSION 1.3.0-p1)
hunter_default_version(eos VERSION 0.12.1)
hunter_default_version(etc2comp VERSION 0.0.0-9cd0f9c-p0)
hunter_default_version(ethash VERSION 1.0.0)
hunter_default_version(eventpp VERSION 0.1.2-for-hunter-pm)
hunter_default_version(eyalroz_printf VERSION 6.2.0)
hunter_default_version(farmhash VERSION 1.1)
hunter_default_version(fast_obj VERSION 1.1-9255172-p0)
hunter_default_version(ffmpeg VERSION n4.1-dev-45499e557c-p7)
hunter_default_version(fft2d VERSION 1.0.0-p0)
hunter_default_version(filament VERSION 1.9.8)
hunter_default_version(fixesproto VERSION 5.0)
hunter_default_version(flatbuffers VERSION 2.0.0)
hunter_default_version(flex VERSION 2.6.4)
hunter_default_version(fmt VERSION 10.1.1)
hunter_default_version(folly VERSION 2018.10.22.00-p4)
hunter_default_version(freetype VERSION 2.10.4-p0)
hunter_default_version(freetype-gl VERSION 0.0.0-1a8c007-p0)
hunter_default_version(frugally-deep VERSION 0.2.2-p0)
hunter_default_version(gRPC VERSION 1.44.0-p0)
hunter_default_version(gauze VERSION 0.7.1)
hunter_default_version(gemmlowp VERSION 1.0.0)
hunter_default_version(geos VERSION 3.4.2)
hunter_default_version(getopt VERSION 1.0.0-p0)
hunter_default_version(gflags VERSION 2.2.2)
hunter_default_version(giflib VERSION 5.2.1-p0)
hunter_default_version(gl4es VERSION 1.1.4-p1)
hunter_default_version(glbinding VERSION 3.1.0-p0)
hunter_default_version(glew VERSION 2.0.0-p1)
hunter_default_version(glfw VERSION 3.3.4-p0)
hunter_default_version(glib VERSION 2.54.0)
hunter_default_version(glm VERSION 0.9.9.8)
hunter_default_version(globjects VERSION 1.1.0-p0)
hunter_default_version(glog VERSION 0.6.0)
hunter_default_version(glproto VERSION 1.4.17)
hunter_default_version(glslang VERSION 8.13.3743-9eef54b2-p0)
hunter_default_version(glu VERSION 9.0.1-p1)
hunter_default_version(gsl-lite VERSION 0.40.0-p0)
hunter_default_version(gst_plugins_bad VERSION 1.10.4)
hunter_default_version(gst_plugins_base VERSION 1.10.4)
hunter_default_version(gst_plugins_good VERSION 1.10.4)
hunter_default_version(gst_plugins_ugly VERSION 1.10.4)
hunter_default_version(gstreamer VERSION 1.10.4)
hunter_default_version(gumbo VERSION 0.10.1)
hunter_default_version(h3 VERSION 3.0.7)
hunter_default_version(half VERSION 1.1.0-p1)
hunter_default_version(harfbuzz VERSION 2.9.1-p0)
hunter_default_version(hdf5 VERSION 1.8.15-p1)
hunter_default_version(highwayhash VERSION 0.0.0)
hunter_default_version(http-parser VERSION 2.8.0)
hunter_default_version(hunter_venv VERSION 1.0.2)
hunter_default_version(hypre VERSION 2.22.0)
hunter_default_version(ice VERSION 1.0.9)
hunter_default_version(icu-le-hb VERSION 1.0.3-231788a-p0)
hunter_default_version(icu-lx VERSION 63.1-p1)
hunter_default_version(imagequant VERSION 2.15.1-p0)
hunter_default_version(imgui VERSION 1.70.p0)
hunter_default_version(imshow VERSION 1.0.0-p0)
hunter_default_version(inja VERSION 0.1.1)
hunter_default_version(inputproto VERSION 2.3)
hunter_default_version(intltool VERSION 0.51.0)
hunter_default_version(intsizeof VERSION 2.0.2)
hunter_default_version(intx VERSION 0.9.0)
hunter_default_version(ios_sim VERSION 3.1.1)
if(MSVC)
  hunter_default_version(ippicv VERSION 20240201)
else()
  # see OpenCV for more info
  hunter_default_version(ippicv VERSION 20230330)
endif()
hunter_default_version(iroha-ed25519 VERSION 2.0.0)
hunter_default_version(irrXML VERSION 1.2-p0)
hunter_default_version(ittapi VERSION 3.21.2-p0)
hunter_default_version(jaegertracing VERSION 0.4.1)
hunter_default_version(jansson VERSION 2.11.0)
hunter_default_version(jasper VERSION 2.0.32-p0)
hunter_default_version(jo_jpeg VERSION 0.0.1)
hunter_default_version(jpeg-compressor VERSION 0.0.0-aeb7d3b-p0)
hunter_default_version(jsmn VERSION 1.1.0-053d3cd-p0)

if(MSVC_VERSION LESS 1600)
  # for VS10 - version without support C++11
  hunter_default_version(jsoncpp VERSION 0.7.0)
else()
  hunter_default_version(jsoncpp VERSION 1.9.5-b1)
endif()

hunter_default_version(jwt-cpp VERSION 0.6.0)
hunter_default_version(kNet VERSION 2.7-p1)
hunter_default_version(kbproto VERSION 1.0.7)
hunter_default_version(lcms VERSION 2.13.1-p0)
hunter_default_version(lehrfempp VERSION 0.8.0)
hunter_default_version(leveldb VERSION 1.22-p1)
hunter_default_version(libarchive VERSION 3.4.3)
hunter_default_version(libbacktrace VERSION 1.0.0-ca0de051)
hunter_default_version(libcpuid VERSION 0.4.0)
hunter_default_version(libdaemon VERSION 0.14)
hunter_default_version(libdill VERSION 1.6)
hunter_default_version(libevhtp VERSION 1.2.16-p4)
hunter_default_version(libffi VERSION 3.2.1)
hunter_default_version(libigl VERSION 2.2.0)
hunter_default_version(libjpeg-turbo VERSION 2.1.0)
hunter_default_version(libjson-rpc-cpp VERSION 0.7.0-p3)
hunter_default_version(libmill VERSION 1.18)
hunter_default_version(libogg VERSION 1.3.3-p0)
hunter_default_version(libpcre VERSION 8.41)
hunter_default_version(librtmp VERSION 2.4.0-p0)
hunter_default_version(libscrypt VERSION 1.21-p1)
hunter_default_version(libsodium VERSION 1.0.16-p0)
hunter_default_version(libunibreak VERSION 4.0)
hunter_default_version(libusb VERSION 1.0.23)
hunter_default_version(libuv VERSION 1.42.0-p0)
hunter_default_version(libxdg-basedir VERSION 1.2.3)
hunter_default_version(libxml2 VERSION 2.9.7-p0)
hunter_default_version(libyuv VERSION 1514-p3)
hunter_default_version(libzip VERSION 1.5.2-d68a667-p0)
hunter_default_version(lmdb VERSION 0.9.21-p2)
hunter_default_version(lmdbxx VERSION 0.9.14.0)
hunter_default_version(log4cplus VERSION 1.2.0-p0)
hunter_default_version(lss VERSION 0.0.0-e1e7b0a-p0)
hunter_default_version(lz4 VERSION 1.9.2-p0)
hunter_default_version(lzma VERSION 5.2.3-p4)
hunter_default_version(magnum VERSION 2019.01)
hunter_default_version(md5 VERSION 1.6)
hunter_default_version(meshoptimizer VERSION 0.16-86740c2-p0)
hunter_default_version(mini_chromium VERSION 0.0.1-p2)
hunter_default_version(miniz VERSION 3.0.2)
hunter_default_version(minizip VERSION 1.0.1-p3)
hunter_default_version(mkl VERSION 20190502)
hunter_default_version(mkldnn VERSION 0.19-p0)
hunter_default_version(mng VERSION 2.0.3-p2)
hunter_default_version(mojoshader VERSION 0.0.1)
hunter_default_version(mongoose VERSION 6.10)
hunter_default_version(mpark_variant VERSION 1.0.0)
hunter_default_version(msgpack VERSION 1.4.1-p2)
hunter_default_version(mshadow VERSION 1.1-1d79ecf-p0)
hunter_default_version(mtplz VERSION 0.1-p3)
hunter_default_version(mxnet VERSION 1.5.0.rc1-b64e00a-p0)
hunter_default_version(nanoflann VERSION 1.2.3-p0)
hunter_default_version(nanosvg VERSION 0.0.0-2b08dee-p0)
hunter_default_version(ncnn VERSION 20180314-p2)
hunter_default_version(ncursesw VERSION 6.1)
hunter_default_version(nlohmann_fifo_map VERSION 0.0.0-0dfbf5d-p1)
hunter_default_version(nlohmann_json VERSION 3.11.2)
hunter_default_version(nng VERSION 1.1.1)
hunter_default_version(nsync VERSION 1.14-p1)
hunter_default_version(occt VERSION 7.4.0-p0)
hunter_default_version(odb VERSION 2.4.0)
hunter_default_version(odb-boost VERSION 2.4.0)
hunter_default_version(odb-compiler VERSION 2.4.0)
hunter_default_version(odb-mysql VERSION 2.4.0)
hunter_default_version(odb-pgsql VERSION 2.4.0)
hunter_default_version(odb-sqlite VERSION 2.4.0)
hunter_default_version(ogles_gpgpu VERSION 0.3.6)
hunter_default_version(oneTBB VERSION 2021.5.0)
hunter_default_version(oniguruma VERSION 6.8.1-p0)
hunter_default_version(onmt VERSION 0.4.1-p2)
hunter_default_version(openddlparser VERSION 0.1.0-p2)
hunter_default_version(opentracing-cpp VERSION 1.6.0)
hunter_default_version(opusfile VERSION 0.12-p2)
hunter_default_version(pcg VERSION 0.0.0-p1)
hunter_default_version(pciaccess VERSION 0.13.4)
hunter_default_version(pcre2 VERSION 10.13-p0)
hunter_default_version(pegtl VERSION 2.8.1)

# pip packages
hunter_default_version(pip_GitPython VERSION 2.1.11)
hunter_default_version(pip_astroid VERSION 2.2.5)
hunter_default_version(pip_boto3 VERSION 1.9.130)
hunter_default_version(pip_botocore VERSION 1.12.130)
hunter_default_version(pip_certifi VERSION 2019.3.9)
hunter_default_version(pip_chardet VERSION 3.0.4)
hunter_default_version(pip_cpplint VERSION 1.4.4)
hunter_default_version(pip_decorator VERSION 4.4.0)
hunter_default_version(pip_gitdb VERSION 2.0.5)
hunter_default_version(pip_idna VERSION 2.8)
hunter_default_version(pip_jmespath VERSION 0.9.4)
hunter_default_version(pip_lazy-object-proxy VERSION 1.3.1)
hunter_default_version(pip_nose VERSION 1.3.7)
hunter_default_version(pip_nose-timer VERSION 0.7.5)
hunter_default_version(pip_numpy VERSION 1.17.5)
hunter_default_version(pip_pylint VERSION 2.3.1)
hunter_default_version(pip_python-dateutil VERSION 2.8.0)
hunter_default_version(pip_requests VERSION 2.21.0)
hunter_default_version(pip_six VERSION 1.12.0)
hunter_default_version(pip_smmap VERSION 2.0.5)
hunter_default_version(pip_urllib3 VERSION 1.24.1)
hunter_default_version(pip_wrapt VERSION 1.11.1)

hunter_default_version(pluginlib VERSION 1.12.1-p0)
hunter_default_version(poly2tri VERSION 1.0.0)
hunter_default_version(polyclipping VERSION 4.8.8-p0) # for Assimp
hunter_default_version(presentproto VERSION 1.0)
hunter_default_version(prometheus-cpp VERSION 0.6.0-p2)
hunter_default_version(protobuf-c VERSION 1.3.0-p1)
hunter_default_version(pthread-stubs VERSION 0.4)
hunter_default_version(pthreads-win32 VERSION 2.9.1-7ad2af7-p0)
hunter_default_version(pugixml VERSION 1.10-p0)
hunter_default_version(pybind11 VERSION 2.11.1)
hunter_default_version(qhull VERSION 7.2.0-p1)
hunter_default_version(quickjs VERSION 2020-04-12-p0)
hunter_default_version(rabbitmq-c VERSION 0.10.0)
hunter_default_version(rabit VERSION 0.0.0-p2)
hunter_default_version(randrproto VERSION 1.3.2)
hunter_default_version(rang VERSION 3.1.0-p0)

if(MSVC)
  if(MSVC_VERSION LESS 1916)
    hunter_default_version(range-v3 VERSION vcpkg5-p)
  else()
    hunter_default_version(range-v3 VERSION 0.12.0)
  endif()
else()
  hunter_default_version(range-v3 VERSION 0.12.0)
endif()

hunter_default_version(re2 VERSION 2023.03.01)
hunter_default_version(readline VERSION 6.3)
hunter_default_version(recastnavigation VERSION 1.4-p0)
hunter_default_version(renderproto VERSION 0.11.1)
hunter_default_version(rocksdb VERSION 7.5.3)
hunter_default_version(ros VERSION 1.14.6-p0)
hunter_default_version(ros_comm VERSION 1.14.3-p1)
hunter_default_version(ros_comm_msgs VERSION 1.11.2-p0)
hunter_default_version(ros_common_msgs VERSION 1.12.7-p0)
hunter_default_version(ros_console_bridge VERSION 0.4.3-p0)
hunter_default_version(ros_environment VERSION 1.2.1-p0)
hunter_default_version(ros_gencpp VERSION 0.6.2-p0)
hunter_default_version(ros_geneus VERSION 2.2.6-p0)
hunter_default_version(ros_genlisp VERSION 0.4.16-p0)
hunter_default_version(ros_genmsg VERSION 0.5.12-p0)
hunter_default_version(ros_gennodejs VERSION 2.0.1-p0)
hunter_default_version(ros_genpy VERSION 0.6.8-p0)
hunter_default_version(ros_message_generation VERSION 0.4.0-p0)
hunter_default_version(ros_message_runtime VERSION 0.4.12-p0)
hunter_default_version(ros_std_msgs VERSION 0.5.12-p0)
hunter_default_version(rosconsole VERSION 1.13.10-p0)
hunter_default_version(roscpp_core VERSION 0.6.12-p0)
hunter_default_version(rospack VERSION 2.5.3-p0)
hunter_default_version(s3 VERSION 4.1.0-287e4be-p1)
hunter_default_version(scelta VERSION 0.1.0-a0f4f70-p0)
hunter_default_version(sds VERSION 2.0.0)
hunter_default_version(sentencepiece VERSION 0.1.8-p1)
hunter_default_version(sentry VERSION 0.4.9-p0)
hunter_default_version(shaderc VERSION 2019.0-p1)
hunter_default_version(shaka_player_embedded VERSION 0.1.0-beta-p1)
hunter_default_version(sleef VERSION 3.3.1-p1)
hunter_default_version(sm VERSION 1.2.3)
hunter_default_version(smol-v VERSION 0.0.0-4b52c16-p0)
hunter_default_version(soil VERSION 1.0.4)
hunter_default_version(sources_for_android_sdk_packer VERSION 1.0.0)
hunter_default_version(sparsehash VERSION 2.0.2)

if(MSVC_VERSION LESS 1800)
  # for VS12 - version without support C++11
  hunter_default_version(spdlog VERSION 1.0.0-p0)
else()
  hunter_default_version(spdlog VERSION 1.12.0-p0)
endif()

hunter_default_version(spirv-cross VERSION 20210115)
hunter_default_version(sqlite3 VERSION 3.43.2-p0)
hunter_default_version(sse2neon VERSION 1.0.0-p0)
hunter_default_version(stanhull VERSION 0.0.1)
hunter_default_version(state_machine VERSION 1.1)
hunter_default_version(stb VERSION 0.0.0-80c8f6a-p0)
hunter_default_version(stdext-path VERSION 0.0.1-p0)
hunter_default_version(stormlib VERSION 9.21-p1)
hunter_default_version(sugar VERSION 1.3.0)
hunter_default_version(szip VERSION 2.1.0-p1)
hunter_default_version(tacopie VERSION 3.2.0-h1)
hunter_default_version(taocpp-json VERSION 1.0.0-beta.11-e0895587)
hunter_default_version(taskflow VERSION 3.3.0)
hunter_default_version(tcl VERSION core8.6.8)
hunter_default_version(termcolor VERSION 1.0.1)
hunter_default_version(tf VERSION 1.12.0-p0)
hunter_default_version(tf2 VERSION 0.6.5-p0)
hunter_default_version(theora VERSION 1.1.1-p0)
hunter_default_version(thread-pool-cpp VERSION 1.1.0)
hunter_default_version(thrift VERSION 0.12.0-p0)
hunter_default_version(tiny-process-library VERSION 2.0.2-p0)
hunter_default_version(tinydir VERSION 1.2-p0)
hunter_default_version(tinyexr VERSION 1.0.0-3c33352-p1)
hunter_default_version(tinygltf VERSION 2.5.0-p0)
hunter_default_version(tinyobjloader VERSION 2.0.0-rc6-bec38e3)
hunter_default_version(tinyrefl VERSION 0.4.1-p0)
hunter_default_version(tinyxml2 VERSION 9.0.0)
hunter_default_version(tmxparser VERSION 2.1.0-ab4125b-p1)
hunter_default_version(toluapp VERSION 1.0.93-p1)
hunter_default_version(tomcrypt VERSION 1.18.2-p1)
hunter_default_version(tommath VERSION 1.0.1-p0)
hunter_default_version(tsl_hat_trie VERSION 0.6.0-1739fa1-p0)
hunter_default_version(tsl_robin_map VERSION 0.6.3-dc2023b)
hunter_default_version(tvm VERSION 0.5-a4bc50e-p0)
hunter_default_version(type_safe VERSION 0.2.1-p2)
hunter_default_version(units VERSION 2.3.1)
hunter_default_version(uriparser VERSION 0.9.5)
hunter_default_version(utf8 VERSION 3.1.1)
hunter_default_version(util_linux VERSION 2.30.1)
hunter_default_version(uuid VERSION 1.0.3)
hunter_default_version(v8 VERSION 7.4.98-p3)
hunter_default_version(vectorial VERSION 0.0.0-ae7dc88-p0)
hunter_default_version(vorbis VERSION 1.3.6-p1)
hunter_default_version(vurtun-lib VERSION 0.0.0-f1cda26-p0)
hunter_default_version(websocketpp VERSION 0.8.1-p0)
hunter_default_version(wt VERSION 4.0.4-p0)
hunter_default_version(wxWidgets VERSION 3.0.2)
hunter_default_version(wyrm VERSION 0.1.0)
hunter_default_version(x11 VERSION 1.6.7)
hunter_default_version(x264 VERSION snapshot-20190513-2245)
hunter_default_version(xatlas VERSION 0.0.0-4077f0e-p0)
hunter_default_version(xau VERSION 1.0.9)
hunter_default_version(xcb VERSION 1.13)
hunter_default_version(xcb-proto VERSION 1.13)
hunter_default_version(xcursor VERSION 1.1.13)
hunter_default_version(xdamage VERSION 1.1.4)
hunter_default_version(xext VERSION 1.3.1)
hunter_default_version(xextproto VERSION 7.3.0)
hunter_default_version(xf86vidmodeproto VERSION 2.3.1)
hunter_default_version(xfixes VERSION 5.0.3)
hunter_default_version(xgboost VERSION 0.7.0-p4)
hunter_default_version(xi VERSION 1.6.1)
hunter_default_version(xinerama VERSION 1.1.2)
hunter_default_version(xineramaproto VERSION 1.1.2)
hunter_default_version(xorg-macros VERSION 1.19.2)
hunter_default_version(xproto VERSION 7.0.31)
hunter_default_version(xrandr VERSION 1.3.2)
hunter_default_version(xrender VERSION 0.9.7)
hunter_default_version(xshmfence VERSION 1.3)
hunter_default_version(xtrans VERSION 1.4.0)
hunter_default_version(xxHash VERSION 0.8.2)
hunter_default_version(xxf86vm VERSION 1.1.2)
hunter_default_version(yaml-cpp VERSION 0.6.3)
hunter_default_version(zip VERSION 0.1.15)
hunter_default_version(zlog VERSION 1.2.14)
hunter_default_version(zookeeper VERSION 3.4.9-p2)
hunter_default_version(zstd VERSION 1.5.5)

if(ANDROID)
  string(COMPARE EQUAL "${CMAKE_SYSTEM_VERSION}" "" _is_empty)
  if(_is_empty)
    hunter_user_error("CMAKE_SYSTEM_VERSION is empty")
  endif()

  string(COMPARE EQUAL "${CMAKE_SYSTEM_VERSION}" "24" _is_api_24)
  string(COMPARE EQUAL "${CMAKE_SYSTEM_VERSION}" "22" _is_api_22)
  string(COMPARE EQUAL "${CMAKE_SYSTEM_VERSION}" "21" _is_api_21)
  string(COMPARE EQUAL "${CMAKE_SYSTEM_VERSION}" "19" _is_api_19)
  string(COMPARE EQUAL "${CMAKE_SYSTEM_VERSION}" "16" _is_api_16)

  set(__HUNTER_LAST_DEFAULT_VERSION_NAME "") # Reset alphabetical order checker

  if(_is_api_21)
    hunter_default_version(Android-ARM-EABI-v7a-System-Image VERSION 21_r04)
    hunter_default_version(Android-Google-APIs VERSION 21_r01)
    hunter_default_version(Android-Google-APIs-Intel-x86-Atom-System-Image VERSION 21_r10)
    hunter_default_version(Android-Intel-x86-Atom-System-Image VERSION 21_r05)
    hunter_default_version(Android-SDK-Platform VERSION 21_r02)
    hunter_default_version(Sources-for-Android-SDK VERSION 21)
  elseif(_is_api_19)
    hunter_default_version(Android-ARM-EABI-v7a-System-Image VERSION 19_r05)
    hunter_default_version(Android-Google-APIs VERSION 19_r18)
    hunter_default_version(Android-Intel-x86-Atom-System-Image VERSION 19)
    hunter_default_version(Android-SDK-Platform VERSION 19_r04)
    hunter_default_version(Sources-for-Android-SDK VERSION 19)
  elseif(_is_api_16)
    hunter_default_version(Android-ARM-EABI-v7a-System-Image VERSION 16_r04)
    hunter_default_version(Android-Google-APIs VERSION 16_r04)
    hunter_default_version(Android-Intel-x86-Atom-System-Image VERSION 16)
    hunter_default_version(Android-MIPS-System-Image VERSION 16_r04)
    hunter_default_version(Android-SDK-Platform VERSION 16_r05)
    hunter_default_version(Sources-for-Android-SDK VERSION 16)
  elseif(_is_api_22)
    hunter_default_version(Android-ARM-EABI-v7a-System-Image VERSION 22_r02)
    hunter_default_version(Android-Google-APIs VERSION 22_r01)
    hunter_default_version(Android-Google-APIs-Intel-x86-Atom-System-Image VERSION 22_r21)
    hunter_default_version(Android-Intel-x86-Atom-System-Image VERSION 22_r06)
    hunter_default_version(Android-SDK-Platform VERSION 22_r02)
    hunter_default_version(Sources-for-Android-SDK VERSION 22)
  elseif(_is_api_24)
    hunter_default_version(Android-ARM-EABI-v7a-System-Image VERSION 24_r07)
    hunter_default_version(Android-ARM64-v8a-System-Image VERSION 24_r07)
    hunter_default_version(Android-Google-APIs VERSION 24_r1)
    hunter_default_version(Android-Google-APIs-Intel-x86-Atom-System-Image VERSION 24_r20)
    hunter_default_version(Android-Intel-x86-Atom-System-Image VERSION 24_r08)
    hunter_default_version(Android-SDK-Platform VERSION 24_r02)
    hunter_default_version(Sources-for-Android-SDK VERSION 24)
  else()
    # TODO: Add more versions
  endif()
endif()
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ cat $HUNTER_ROOT/cmake/projects/GTest/hunter.cmake
# Copyright (c) 2013, Ruslan Baratov
# All rights reserved.

# !!! DO NOT PLACE HEADER GUARDS HERE !!!

include(hunter_add_version)
include(hunter_cacheable)
include(hunter_download)
include(hunter_pick_scheme)
include(hunter_cmake_args)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.7.0-hunter"
    URL
    "https://github.com/hunter-packages/gtest/archive/v1.7.0-hunter.tar.gz"
    SHA1
    1ed1c26d11fb592056c1cb912bd3c784afa96eaa
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.7.0-hunter-1"
    URL
    "https://github.com/hunter-packages/gtest/archive/v1.7.0-hunter-1.tar.gz"
    SHA1
    0cb1dcf75e144ad052d3f1e4923a7773bf9b494f
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.7.0-hunter-2"
    URL
    "https://github.com/hunter-packages/gtest/archive/v1.7.0-hunter-2.tar.gz"
    SHA1
    e62b2ef70308f63c32c560f7b6e252442eed4d57
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.7.0-hunter-3"
    URL
    "https://github.com/hunter-packages/gtest/archive/v1.7.0-hunter-3.tar.gz"
    SHA1
    fea7d3020e20f059255484c69755753ccadf6362
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.7.0-hunter-4"
    URL
    "https://github.com/hunter-packages/gtest/archive/v1.7.0-hunter-4.tar.gz"
    SHA1
    9b439c0c25437a083957b197ac6905662a5d901b
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.7.0-hunter-5"
    URL
    "https://github.com/hunter-packages/gtest/archive/v1.7.0-hunter-5.tar.gz"
    SHA1
    796804df3facb074087a4d8ba6f652e5ac69ad7f
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.7.0-hunter-6"
    URL
    "https://github.com/hunter-packages/gtest/archive/v1.7.0-hunter-6.tar.gz"
    SHA1
    64b93147abe287da8fe4e18cfd54ba9297dafb82
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.7.0-hunter-7"
    URL
    "https://github.com/hunter-packages/gtest/archive/v1.7.0-hunter-7.tar.gz"
    SHA1
    19b5c98747768bcd0622714f2ed40f17aee406b2
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.7.0-hunter-8"
    URL
    "https://github.com/hunter-packages/gtest/archive/v1.7.0-hunter-8.tar.gz"
    SHA1
    ac4d2215aa1b1d745a096e5e3b2dbe0c0f229ea5
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.7.0-hunter-9"
    URL
    "https://github.com/hunter-packages/gtest/archive/v1.7.0-hunter-9.tar.gz"
    SHA1
    8a47fe9c4e550f4ed0e2c05388dd291a059223d9
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.7.0-hunter-10"
    URL
    "https://github.com/hunter-packages/gtest/archive/v1.7.0-hunter-10.tar.gz"
    SHA1
    374e6dbe8619ab467c6b1a0b470a598407b172e9
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.7.0-hunter-11"
    URL
    "https://github.com/hunter-packages/gtest/archive/v1.7.0-hunter-11.tar.gz"
    SHA1
    c6ae948ca2bea1d734af01b1069491b00933ed31
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    1.8.0-hunter-p2
    URL
    "https://github.com/hunter-packages/googletest/archive/1.8.0-hunter-p2.tar.gz"
    SHA1
    93148cb8850abe78b76ed87158fdb6b9c48e38c4
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    1.8.0-hunter-p5
    URL https://github.com/hunter-packages/googletest/archive/1.8.0-hunter-p5.tar.gz
    SHA1 3325aa4fc8b30e665c9f73a60f19387b7db36f85
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    1.8.0-hunter-p6
    URL
    "https://github.com/hunter-packages/googletest/archive/1.8.0-hunter-p6.tar.gz"
    SHA1
    f57096bd01c6f8cbef043b312d4d1e82f29648b6
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    1.8.0-hunter-p7
    URL
    "https://github.com/hunter-packages/googletest/archive/1.8.0-hunter-p7.tar.gz"
    SHA1
    4fe083a96d7597f7dce6f453dca01e1d94a1e45b
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    1.8.0-hunter-p8
    URL
    "https://github.com/hunter-packages/googletest/archive/1.8.0-hunter-p8.tar.gz"
    SHA1
    1cdd396b20c8d29f7ea08baaa49673b1c261f545
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    1.8.0-hunter-p9
    URL
    "https://github.com/hunter-packages/googletest/archive/1.8.0-hunter-p9.tar.gz"
    SHA1
    a345f16cb610e0b5dfa7778dc2852b784cfede5b
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    1.8.0-hunter-p10
    URL
    "https://github.com/hunter-packages/googletest/archive/1.8.0-hunter-p10.tar.gz"
    SHA1
    1d92c9f51af756410843b13f8c4e4df09e235394
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.8.0-hunter-p11"
    URL
    "https://github.com/hunter-packages/googletest/archive/1.8.0-hunter-p11.tar.gz"
    SHA1
    76c6aec038f7d7258bf5c4f45c4817b34039d285
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.8.1"
    URL
    "https://github.com/google/googletest/archive/release-1.8.1.tar.gz"
    SHA1
    152b849610d91a9dfa1401293f43230c2e0c33f8
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.10.0"
    URL
    "https://github.com/google/googletest/archive/release-1.10.0.tar.gz"
    SHA1
    9c89be7df9c5e8cb0bc20b3c4b39bf7e82686770
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.10.0-p0"
    URL
    "https://github.com/hunter-packages/googletest/archive/v1.10.0-p0.tar.gz"
    SHA1
    f7c72be12120e018f53cda0e0daa26fab5da7dfc
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.10.0-p1"
    URL
    "https://github.com/hunter-packages/googletest/archive/v1.10.0-p1.tar.gz"
    SHA1
    06a1f667f200ff94d38b608e44c3c8061c7b8f2f
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.11.0"
    URL
    "https://github.com/google/googletest/archive/release-1.11.0.tar.gz"
    SHA1
    7b100bb68db8df1060e178c495f3cbe941c9b058
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.12.1"
    URL
    "https://github.com/google/googletest/archive/release-1.12.1.tar.gz"
    SHA1
    cdddd449d4e3aa7bd421d4519c17139ea1890fe7
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.13.0"
    URL
    "https://github.com/google/googletest/archive/v1.13.0.tar.gz"
    SHA1
    bfa4b5131b6eaac06962c251742c96aab3f7aa78
)

hunter_add_version(
    PACKAGE_NAME
    GTest
    VERSION
    "1.14.0"
    URL
    "https://github.com/google/googletest/archive/v1.14.0.tar.gz"
    SHA1
    2b28c2a3a30d86b1759543ef61fac3c4d69f8c4c
)

hunter_add_version(
        PACKAGE_NAME
        GTest
        VERSION
        "1.15.2"
        URL
        "https://github.com/google/googletest/archive/v1.15.2.tar.gz"
        SHA1
        568d58e26bd4e838449ca7ab8ebc152b3cbd210d
)


if(HUNTER_GTest_VERSION VERSION_LESS 1.8.0 OR HUNTER_GTest_VERSION VERSION_GREATER_EQUAL 1.11.0)
  set(_gtest_license "LICENSE")
else()
  set(_gtest_license "googletest/LICENSE")
endif()

# gtest_force_shared_crt prevents GoogleTest from modifying options
# rather than forcing it to use shared libraries
hunter_cmake_args(
    GTest
    CMAKE_ARGS
    HUNTER_INSTALL_LICENSE_FILES=${_gtest_license}
    gtest_force_shared_crt=TRUE
)

hunter_pick_scheme(DEFAULT url_sha1_cmake)
hunter_cacheable(GTest)
hunter_download(PACKAGE_NAME GTest PACKAGE_INTERNAL_DEPS_ID 1)
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ mkdir cmake/Hunter
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ cat > cmake/Hunter/config.cmake <<EOF
> hunter_config(GTest VERSION 1.7.0-hunter-9)
EOF
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ mkdir demo
mkdir: невозможно создать каталог «demo»: Файл существует
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ cat > demo/main.cpp <<EOF
> #include <print.hpp>

#include <cstdlib>

int main(int argc, char* argv[])
{
  const char* log_path = std::getenv("LOG_PATH");
  if (log_path == nullptr)
  {
    std::cerr << "undefined environment variable: LOG_PATH" << std::endl;
    return 1;
  }
  std::string text;
  while (std::cin >> text)
  {
    std::ofstream out{log_path, std::ios_base::app};
    print(text, out);
    out << std::endl;
  }
}
EOF
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ gsed -i '/endif()/a\
> add_executable(demo ${CMAKE_CURRENT_SOURCE_DIR}/demo/main.cpp)
target_link_libraries(demo print)
install(TARGETS demo RUNTIME DESTINATION bin)
' CMakeLists.txt
sed: -e выражение #1, символ 104: лишние символы после команды
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ gsed -i '/endif()/a \
> add_executable(demo ${CMAKE_CURRENT_SOURCE_DIR}/demo/main.cpp)\
target_link_libraries(demo print)\
install(TARGETS demo RUNTIME DESTINATION bin)' CMakeLists.txt
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ mkdir tools
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git submodule add https://github.com/ruslo/polly tools/polly
Клонирование в «/home/luka/Joker762-rgb/workspace/projects/lab07/tools/polly»...
remote: Enumerating objects: 6578, done.
remote: Counting objects: 100% (32/32), done.
remote: Compressing objects: 100% (15/15), done.
remote: Total 6578 (delta 21), reused 20 (delta 17), pack-reused 6546 (from 1)
Получение объектов: 100% (6578/6578), 1.68 МиБ | 910.00 КиБ/с, готово.
Определение изменений: 100% (4551/4551), готово.
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ tools/polly/bin/polly.py --test
Python version: 3.12
Build dir: /home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default
Execute command: [
  `which`
  `cmake`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "which" "cmake"

/usr/bin/cmake
Execute command: [
  `cmake`
  `--version`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "cmake" "--version"

cmake version 3.28.3

CMake suite maintained and supported by Kitware (kitware.com/cmake).
Execute command: [
  `cmake`
  `-H.`
  `-B/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default`
  `-DCMAKE_TOOLCHAIN_FILE=/home/luka/Joker762-rgb/workspace/projects/lab07/tools/polly/default.cmake`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "cmake" "-H." "-B/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default" "-DCMAKE_TOOLCHAIN_FILE=/home/luka/Joker762-rgb/workspace/projects/lab07/tools/polly/default.cmake"

CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- [polly] Used toolchain: Default
-- The C compiler identification is GNU 13.3.0
-- The CXX compiler identification is GNU 13.3.0
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
-- [hunter] Calculating Toolchain-SHA1
-- [hunter] Calculating Config-SHA1
-- [hunter] HUNTER_ROOT: /home/luka/projects/hunter
-- [hunter] [ Hunter-ID: xxxxxxx | Toolchain-ID: fb15dbb | Config-ID: d14f46d ]
-- [hunter] GTEST_ROOT: /home/luka/projects/hunter/_Base/xxxxxxx/fb15dbb/d14f46d/Install (ver.: 1.15.2)
-- Found GTest: /home/luka/projects/hunter/_Base/xxxxxxx/fb15dbb/d14f46d/Install/lib/cmake/GTest/GTestConfig.cmake (found version "1.15.2")
CMake Error at CMakeLists.txt:66 (add_executable):
  add_executable cannot create target "demo" because another target with the
  same name already exists.  The existing target is an executable created in
  source directory "/home/luka/Joker762-rgb/workspace/projects/lab07".
  See documentation for policy CMP0002 for more details.


CMake Error at CMakeLists.txt:70 (add_executable):
  add_executable cannot create target "demo" because another target with the
  same name already exists.  The existing target is an executable created in
  source directory "/home/luka/Joker762-rgb/workspace/projects/lab07".
  See documentation for policy CMP0002 for more details.


-- Configuring incomplete, errors occurred!
Command exit with status "1": [/home/luka/Joker762-rgb/workspace/projects/lab07]> "cmake" "-H." "-B/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default" "-DCMAKE_TOOLCHAIN_FILE=/home/luka/Joker762-rgb/workspace/projects/lab07/tools/polly/default.cmake"

Log: /home/luka/Joker762-rgb/workspace/projects/lab07/_logs/polly/default/log.txt
*** FAILED ***
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ tools/polly/bin/polly.py --test
Python version: 3.12
Build dir: /home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default
Execute command: [
  `which`
  `cmake`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "which" "cmake"

/usr/bin/cmake
Execute command: [
  `cmake`
  `--version`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "cmake" "--version"

cmake version 3.28.3

CMake suite maintained and supported by Kitware (kitware.com/cmake).
Execute command: [
  `cmake`
  `-H.`
  `-B/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default`
  `-DCMAKE_TOOLCHAIN_FILE=/home/luka/Joker762-rgb/workspace/projects/lab07/tools/polly/default.cmake`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "cmake" "-H." "-B/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default" "-DCMAKE_TOOLCHAIN_FILE=/home/luka/Joker762-rgb/workspace/projects/lab07/tools/polly/default.cmake"

CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- [polly] Used toolchain: Default
-- The C compiler identification is GNU 13.3.0
-- The CXX compiler identification is GNU 13.3.0
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
-- [hunter] Calculating Toolchain-SHA1
-- [hunter] Calculating Config-SHA1
-- [hunter] HUNTER_ROOT: /home/luka/projects/hunter
-- [hunter] [ Hunter-ID: xxxxxxx | Toolchain-ID: fb15dbb | Config-ID: d14f46d ]
-- [hunter] GTEST_ROOT: /home/luka/projects/hunter/_Base/xxxxxxx/fb15dbb/d14f46d/Install (ver.: 1.15.2)
-- Found GTest: /home/luka/projects/hunter/_Base/xxxxxxx/fb15dbb/d14f46d/Install/lib/cmake/GTest/GTestConfig.cmake (found version "1.15.2")
CMake Error at CMakeLists.txt:66 (add_executable):
  add_executable cannot create target "demo" because another target with the
  same name already exists.  The existing target is an executable created in
  source directory "/home/luka/Joker762-rgb/workspace/projects/lab07".
  See documentation for policy CMP0002 for more details.


-- Configuring incomplete, errors occurred!
Command exit with status "1": [/home/luka/Joker762-rgb/workspace/projects/lab07]> "cmake" "-H." "-B/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default" "-DCMAKE_TOOLCHAIN_FILE=/home/luka/Joker762-rgb/workspace/projects/lab07/tools/polly/default.cmake"

Log: /home/luka/Joker762-rgb/workspace/projects/lab07/_logs/polly/default/log.txt
*** FAILED ***
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ tools/polly/bin/polly.py --test
Python version: 3.12
Build dir: /home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default
Execute command: [
  `which`
  `cmake`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "which" "cmake"

/usr/bin/cmake
Execute command: [
  `cmake`
  `--version`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "cmake" "--version"

cmake version 3.28.3

CMake suite maintained and supported by Kitware (kitware.com/cmake).
Execute command: [
  `cmake`
  `-H.`
  `-B/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default`
  `-DCMAKE_TOOLCHAIN_FILE=/home/luka/Joker762-rgb/workspace/projects/lab07/tools/polly/default.cmake`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "cmake" "-H." "-B/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default" "-DCMAKE_TOOLCHAIN_FILE=/home/luka/Joker762-rgb/workspace/projects/lab07/tools/polly/default.cmake"

CMake Error at CMakeLists.txt:58 (if):
  Flow control statements are not properly nested.


-- Configuring incomplete, errors occurred!
Command exit with status "1": [/home/luka/Joker762-rgb/workspace/projects/lab07]> "cmake" "-H." "-B/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default" "-DCMAKE_TOOLCHAIN_FILE=/home/luka/Joker762-rgb/workspace/projects/lab07/tools/polly/default.cmake"

Log: /home/luka/Joker762-rgb/workspace/projects/lab07/_logs/polly/default/log.txt
*** FAILED ***
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ tools/polly/bin/polly.py --test
Python version: 3.12
Build dir: /home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default
Execute command: [
  `which`
  `cmake`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "which" "cmake"

/usr/bin/cmake
Execute command: [
  `cmake`
  `--version`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "cmake" "--version"

cmake version 3.28.3

CMake suite maintained and supported by Kitware (kitware.com/cmake).
Execute command: [
  `cmake`
  `-H.`
  `-B/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default`
  `-DCMAKE_TOOLCHAIN_FILE=/home/luka/Joker762-rgb/workspace/projects/lab07/tools/polly/default.cmake`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "cmake" "-H." "-B/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default" "-DCMAKE_TOOLCHAIN_FILE=/home/luka/Joker762-rgb/workspace/projects/lab07/tools/polly/default.cmake"

CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- [polly] Used toolchain: Default
-- The C compiler identification is GNU 13.3.0
-- The CXX compiler identification is GNU 13.3.0
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
-- [hunter] Calculating Toolchain-SHA1
-- [hunter] Calculating Config-SHA1
-- [hunter] HUNTER_ROOT: /home/luka/projects/hunter
-- [hunter] [ Hunter-ID: xxxxxxx | Toolchain-ID: fb15dbb | Config-ID: d14f46d ]
-- [hunter] GTEST_ROOT: /home/luka/projects/hunter/_Base/xxxxxxx/fb15dbb/d14f46d/Install (ver.: 1.15.2)
-- Found GTest: /home/luka/projects/hunter/_Base/xxxxxxx/fb15dbb/d14f46d/Install/lib/cmake/GTest/GTestConfig.cmake (found version "1.15.2")
-- Configuring done (0.9s)
-- Generating done (0.0s)
-- Build files have been written to: /home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default
Execute command: [
  `cmake`
  `--build`
  `/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default`
  `--`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "cmake" "--build" "/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default" "--"

[ 25%] Building CXX object CMakeFiles/print.dir/sources/print.cpp.o
[ 50%] Linking CXX static library libprint.a
[ 50%] Built target print
[ 75%] Building CXX object CMakeFiles/demo.dir/demo/main.cpp.o
[100%] Linking CXX executable demo
[100%] Built target demo
Run tests
Execute command: [
  `ctest`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default]> "ctest"

*********************************
No test configuration file found!
*********************************
Usage

  ctest [options]

-
Log saved: /home/luka/Joker762-rgb/workspace/projects/lab07/_logs/polly/default/log.txt
-
Generate: 0:00:01.874838s
Build: 0:00:01.504141s
Test: 0:00:00.012541s
-
Total: 0:00:03.391800s
-
SUCCESS
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ tools/polly/bin/polly.py --install
Python version: 3.12
Build dir: /home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default
Execute command: [
  `which`
  `cmake`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "which" "cmake"

/usr/bin/cmake
Execute command: [
  `cmake`
  `--version`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "cmake" "--version"

cmake version 3.28.3

CMake suite maintained and supported by Kitware (kitware.com/cmake).

== WARNING ==

Looks like cmake arguments changed. You have two options to fix it:
  * Remove build directory completely by adding '--clear' (works 100%)
  * Run configure again by adding '--reconfig' (you must understand how CMake cache variables works/updated)

- "cmake" "-H." "-B/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default" "-DCMAKE_TOOLCHAIN_FILE=/home/luka/Joker762-rgb/workspace/projects/lab07/tools/polly/default.cmake"
+ "cmake" "-H." "-B/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/default" "-DCMAKE_TOOLCHAIN_FILE=/home/luka/Joker762-rgb/workspace/projects/lab07/tools/polly/default.cmake" "-DCMAKE_INSTALL_PREFIX=/home/luka/Joker762-rgb/workspace/projects/lab07/_install/default"
?                                                                                                                                                                                             ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ tools/polly/bin/polly.py --toolchain clang-cxx14
Python version: 3.12
Build dir: /home/luka/Joker762-rgb/workspace/projects/lab07/_builds/clang-cxx14
Execute command: [
  `which`
  `cmake`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "which" "cmake"

/usr/bin/cmake
Execute command: [
  `cmake`
  `--version`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "cmake" "--version"

cmake version 3.28.3

CMake suite maintained and supported by Kitware (kitware.com/cmake).
Execute command: [
  `cmake`
  `-H.`
  `-B/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/clang-cxx14`
  `-GUnix Makefiles`
  `-DCMAKE_TOOLCHAIN_FILE=/home/luka/Joker762-rgb/workspace/projects/lab07/tools/polly/clang-cxx14.cmake`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "cmake" "-H." "-B/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/clang-cxx14" "-GUnix Makefiles" "-DCMAKE_TOOLCHAIN_FILE=/home/luka/Joker762-rgb/workspace/projects/lab07/tools/polly/clang-cxx14.cmake"

CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- [polly] Used toolchain: clang / c++14 support
-- The C compiler identification is Clang 18.1.3
-- The CXX compiler identification is Clang 18.1.3
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/clang - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/clang++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- [hunter] Calculating Toolchain-SHA1
-- [hunter] Calculating Config-SHA1
-- [hunter] HUNTER_ROOT: /home/luka/projects/hunter
-- [hunter] [ Hunter-ID: xxxxxxx | Toolchain-ID: 71bad34 | Config-ID: d14f46d ]
-- [hunter] GTEST_ROOT: /home/luka/projects/hunter/_Base/xxxxxxx/71bad34/d14f46d/Install (ver.: 1.15.2)
-- Found GTest: /home/luka/projects/hunter/_Base/xxxxxxx/71bad34/d14f46d/Install/lib/cmake/GTest/GTestConfig.cmake (found version "1.15.2")
-- Configuring done (1.3s)
-- Generating done (0.0s)
-- Build files have been written to: /home/luka/Joker762-rgb/workspace/projects/lab07/_builds/clang-cxx14
Execute command: [
  `cmake`
  `--build`
  `/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/clang-cxx14`
  `--`
]

[/home/luka/Joker762-rgb/workspace/projects/lab07]> "cmake" "--build" "/home/luka/Joker762-rgb/workspace/projects/lab07/_builds/clang-cxx14" "--"

[ 25%] Building CXX object CMakeFiles/print.dir/sources/print.cpp.o
[ 50%] Linking CXX static library libprint.a
[ 50%] Built target print
[ 75%] Building CXX object CMakeFiles/demo.dir/demo/main.cpp.o
[100%] Linking CXX executable demo
[100%] Built target demo
-
Log saved: /home/luka/Joker762-rgb/workspace/projects/lab07/_logs/polly/clang-cxx14/log.txt
-
Generate: 0:00:02.314253s
Build: 0:00:01.591061s
-
Total: 0:00:03.906520s
-
SUCCESS
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab07$ git push origin master
Username for 'https://github.com': Joker762-rgb
Password for 'https://Joker762-rgb@github.com': 
Перечисление объектов: 226, готово.
Подсчет объектов: 100% (226/226), готово.
При сжатии изменений используется до 3 потоков
Сжатие объектов: 100% (115/115), готово.
Запись объектов: 100% (223/223), 1.01 МиБ | 207.55 МиБ/с, готово.
Всего 223 (изменений 84), повторно использовано 217 (изменений 81), повторно использовано пакетов 0
remote: Resolving deltas: 100% (84/84), done.
To https://github.com/Joker762-rgb/lab07
   fc18f3a..5c26ec6  master -> master
