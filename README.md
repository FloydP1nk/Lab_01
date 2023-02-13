# Лабораторная работа №1 ТиМп
Выполнил Ерохин Павел ИУ8-23
#### 1. Установка библиотеки  *boost*
    wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
#### 2. Разархивация
    tar xvzf boost_1_69_0.tar.gz
####  Подсчет количества файлов
    
#### 3. В диреектории *boost_1_69_0* расположено 12 файлов, не включая вложенные директории
    ls -l | grep "^-" | wc             // grep "^-" (учитываем только строки, которые начинаются на дефис)
    tree -L 1

#### 4. В диреектории *boost_1_69_0* расположено 61191 файла, включая вложенные директории
    tree
#### 5.
#### Подсчет файлов с расширением .cpp *(Ответ: 13774)*
    find . -type f -name "*.cpp" | wc -l
    tree -P "*cpp"
#### Подсчет файлов с расширением .hpp *(Ответ: 14912)*
    find . -type f -name "*.hpp" | wc -l
    tree -P "*cpptree -P "*.hpp""
#### Подсчет файлов с расширением .h *(Ответ: 296)*
    find . -type f -name "*.h" | wc -l
    tree -P "*.h"<img width="434" alt="image" src="https://user-images.githubusercontent.com/113801739/218414678-adf96afa-ecc7-4a29-bc6b-7093cc9a8ec9.png">

#### Подсчет всех остальных файлов (Ответ: 32209)
    61191-13774-14912-296=32209 ?
    find . -not -name "*.h" -not -name "*.hpp" -not -name "*.cpp" -not -type d|wc -l
        вывод 32211

#### 6.
    find $PWD -name any.hpp
![Снимок экрана 2023-02-12 в 00 20 24](https://user-images.githubusercontent.com/113801739/218281641-60f5253c-259d-46ef-8e47-29c774462d8b.png)

#### 7. Вывод в консоль всех файлов, где упоминается последовательность *boost::asio*
    grep -rl 'boost::asio'
#### 8. Компиляция *boost*
    cd tools/build
     ./bootstrap.sh
     ////////     ./b2 install --prefix=<DIR>
     ./b2 install --prefix=test

<img width="285" alt="Снимок экрана 2023-02-13 в 13 54 41" src="https://user-images.githubusercontent.com/113801739/218439543-dc9f85ec-c2a4-4bb6-860a-3d16d6ef6a79.png">

#### 9. Перенос скомпилированных файлов
    mkdir ~/boost-lib
    mv -i test /Users/pavelerokhin/boost-libs
#### 10. Подсчет размера каждого файла директории
    du -ah
#### 11. Топ 10 самых тяжелых файлов
    find . -xdev -type f -not -type d -print | xargs ls -lh | sort -k5,5 -h -r | head
