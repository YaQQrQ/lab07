michel@MichelUbuntu:~$ export GITHUB_USERNAME=MichelsonIU815
michel@MichelUbuntu:~$ cd ${GITHUB_USERNAME}/workspace
michel@MichelUbuntu:~/MichelsonIU815/workspace$ pushd .
~/MichelsonIU815/workspace ~/MichelsonIU815/workspace
michel@MichelUbuntu:~/MichelsonIU815/workspace$ source scripts/activate
michel@MichelUbuntu:~/MichelsonIU815/workspace$ . scripts/activate
michel@MichelUbuntu:~/MichelsonIU815/workspace$ git clone https://github.com/${GITHUB_USERNAME}/lab03 projects/test
Клонирование в «projects/test»...
remote: Enumerating objects: 30, done.
remote: Counting objects: 100% (30/30), done.
remote: Compressing objects: 100% (19/19), done.
remote: Total 30 (delta 5), reused 30 (delta 5), pack-reused 0 (from 0)
Получение объектов: 100% (30/30), 7.81 КиБ | 7.81 МиБ/с, готово.
Определение изменений: 100% (5/5), готово.
michel@MichelUbuntu:~/MichelsonIU815/workspace$ cd projects/test
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/test$ git remote remove origin
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/test$ git remote add origin https://github.com/${GITHUB_USERNAME}/test
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/test$ cat > .travis.yml <<EOF
> language: cpp
> EOF
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/test$ cat >> .travis.yml <<EOF
> 
> script:
> - cmake -H. -B_build -DCMAKE_INSTALL_PREFIX=_install
> - cmake --build _build
> - cmake --build _build --target install
> EOF
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/test$ git add .travis.yml
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/test$ git add README.md
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/test$ git commit -m"added CI"
[master 112b76d] added CI
 1 file changed, 6 insertions(+)
 create mode 100644 .travis.yml
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/test$ git push origin master
Username for 'https://github.com': MichelsonIU815
Password for 'https://MichelsonIU815@github.com': 
Перечисление объектов: 33, готово.
Подсчет объектов: 100% (33/33), готово.
При сжатии изменений используется до 12 потоков
Сжатие объектов: 100% (22/22), готово.
Запись объектов: 100% (33/33), 8.11 КиБ | 8.11 МиБ/с, готово.
Всего 33 (изменений 6), повторно использовано 29 (изменений 5), повторно использовано пакетов 0
remote: Resolving deltas: 100% (6/6), done.
To https://github.com/MichelsonIU815/test
 * [new branch]      master -> master
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/test$ rvm --version
rvm 1.29.12 (latest) by Michal Papis, Piotr Kuczynski, Wayne E. Seguin [https://rvm.io]
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/test$ ruby --version
ruby 3.2.3 (2024-01-18 revision 52bb2ac0a6) [x86_64-linux-gnu]
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/test$ 
