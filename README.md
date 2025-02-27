michel@MichelUbuntu:~$ cd ~/MichelsonIU815/workspace/projects/lab02
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ touch .gitignore
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ git add .gitignore
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ git commit -m"added .gitignore"
[master ae248fd] added .gitignore
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 .gitignore
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ git push origin master
Username for 'https://github.com': MichelsonIU815
Password for 'https://MichelsonIU815@github.com': 
Перечисление объектов: 3, готово.
Подсчет объектов: 100% (3/3), готово.
При сжатии изменений используется до 12 потоков
Сжатие объектов: 100% (2/2), готово.
Запись объектов: 100% (2/2), 285 байтов | 285.00 КиБ/с, готово.
Всего 2 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
To https://github.com/MichelsonIU815/lab02.git
   f050301..ae248fd  master -> master
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ git pull origin master
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Распаковка объектов: 100% (3/3), 986 байтов | 986.00 КиБ/с, готово.
Из https://github.com/MichelsonIU815/lab02
 * branch            master     -> FETCH_HEAD
   ae248fd..25f9b84  master     -> origin/master
Обновление ae248fd..25f9b84
Fast-forward
 .gitignore | 4 ++++
 1 file changed, 4 insertions(+)
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ git log
commit 25f9b84f47771b1deb2a1e17eb1e1b8337e93eec (HEAD -> master, origin/master)
Author: MichelsonIU815 <dmtmikel@mail.ru>
Date:   Thu Feb 27 09:20:30 2025 +0300

    Update .gitignore

commit ae248fd0f2bc913aef7d87dfc9e5cd8a73ea1c79
Author: MichelsonIU815 <dmtmikel@mail.ru>
Date:   Thu Feb 27 09:19:28 2025 +0300

    added .gitignore

commit f050301a8a74a6399fedfc843adffe0bd647e6f0
Author: MichelsonIU815 <dmtmikel@mail.ru>
Date:   Thu Feb 27 09:13:16 2025 +0300

    added README.md

commit baf06fa391bd59fa83546d20b651511ee11f3bd1
Author: MichelsonIU815 <dmtmikel@mail.ru>
Date:   Thu Feb 27 09:05:12 2025 +0300

    Initial commit
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ mkdir sources
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ mkdir include
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ mkdir examples
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ cat > source/print.cpp <<EOF
> #include<print.hpp>
> void print(const std::string& text, std::ostream& out) {
>    out << text;
> }
> 
> void print(const std::string& text, std::ofstream& out) {
>    out << text;
> }
> EOF
bash: source/print.cpp: Нет такого файла или каталога
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ cat > sources/print.cpp <<EOF
> cat > source/print.cpp <<EOF
#include<print.hpp>
void print(const std::string& text, std::ostream& out) {
   out << text;
}

void print(const std::string& text, std::ofstream& out) {
   out << text;
}
EOF
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ $ cat > include/print.hpp <<EOF
#include <fstream>
#include <iostream>
#include <string>

void print(const std::string& text, std::ofstream& out);
void print(const std::string& text, std::ostream& out = std::cout);
EOF
$: команда не найдена
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ $ cat > include/print.hpp <<EOF
> #include<fstream>
> #include<iostream>
> #include<string>
> 
> void print(const std::string& text, std::ofstream& out);
> void print(const std::string& text, std::ostream& out = std::cout);
> EOF
$: команда не найдена
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ cat > include/print.hpp <<EOF
> #include<fstream>
> #include<iostream>
> #include<string>
> void print(const std::string& text, std::ofstream& out);
> void print(const std::string& text, std::ostream& out = std::cout);
> EOF
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ cat > examples/example1.cpp <<EOF
> #include<print.hpp>
> int main(int argc, char** argv) {
>    print("hello");
> }
> EOF
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ cat > examples/example2.cpp <<EOF
> #include<print.hpp>
> #include<fstream>
> int main(int argc, char** argv) {
>    std::ofstream file("log.txt");
>    print(std::string("hello"), file);
> }
> EOF
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ edit README.md
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ git status
Текущая ветка: master
Неотслеживаемые файлы:
  (используйте «git add <файл>...», чтобы добавить в то, что будет включено в коммит)
	examples/
	include/
	sources/

индекс пуст, но есть неотслеживаемые файлы
(используйте «git add», чтобы проиндексировать их)
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ git add .
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ git commit -m"added sources"
[master 771b80c] added sources
 4 files changed, 24 insertions(+)
 create mode 100644 examples/example1.cpp
 create mode 100644 examples/example2.cpp
 create mode 100644 include/print.hpp
 create mode 100644 sources/print.cpp
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ git push origin master
Username for 'https://github.com': MichelsonIU815
Password for 'https://MichelsonIU815@github.com': 
Перечисление объектов: 10, готово.
Подсчет объектов: 100% (10/10), готово.
При сжатии изменений используется до 12 потоков
Сжатие объектов: 100% (7/7), готово.
Запись объектов: 100% (9/9), 988 байтов | 988.00 КиБ/с, готово.
Всего 9 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
To https://github.com/MichelsonIU815/lab02.git
   25f9b84..771b80c  master -> master
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab02$ 
