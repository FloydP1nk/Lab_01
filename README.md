# Lab_01cd
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
#### Подсчет файлов с расширением .cpp *(13774)*
    find . -type f -name "*.cpp" | wc -l
    tree -P "*cpp"
#### Подсчет файлов с расширением .hpp *(14912)*
    find . -type f -name "*.hpp" | wc -l
    tree -P "*cpptree -P "*.hpp""
#### Подсчет файлов с расширением .h *(296)*
    find . -type f -name "*.h" | wc -l
    tree -P "*.h"
#### Подсчет всех остальных файлов (32209)
    61191-13774-14912-296=32209 ?
#### 5.
#### 6.
#### 7. Вывод в консоль всех файлов, где упоминается последовательность *boost::asio*
    grep -rl 'boost::asio'
