# TP_lab_01

1 - скачиваю boost через утилиту 
wget

2 - Разархивирую ее спомощью команды  
$tar -xf boost_1_69_0.tar.gz

3 - считаю кол-во директорий в boost не считая вложенные 
$tree boost_1_69_0 -L 1
![image](https://user-images.githubusercontent.com/56314346/157689846-f4322a92-603c-4482-a371-6bed916bcd24.png)

4 - считаю кол_во всех файлов и директорий 
$tree boost_1_69_0 -a
![image](https://user-images.githubusercontent.com/56314346/157690341-041ace78-b508-4a8b-90e4-44376f346f90.png)

5 - считаю кол-во заголовочных файлов (.hpp) все (.cpp) те, что не относятся к (.hpp) и (.cpp)

$tree boost_1_69_0 -P "*.cpp"
![image](https://user-images.githubusercontent.com/56314346/157691341-713d4ff2-fd24-4647-b39b-ae8079b955c7.png)

$tree boost_1_69_0 -P "*.hpp"
![image](https://user-images.githubusercontent.com/56314346/157691431-b89fa659-1c52-421b-bfb9-cfed2ed6b9e5.png)

$tree boost_1_69_0 -I "*.cpp|*.hpp"
![image](https://user-images.githubusercontent.com/56314346/157691515-c1c8962a-72e9-4c4f-9c2d-3e1ce9ce2639.png)

6 - найти путь до "any.hpp"
$find ./boost_1_69_0 -name "any.hpp"
![image](https://user-images.githubusercontent.com/56314346/157691431-b89fa659-1c52-421b-bfb9-cfed2ed6b9e5.png)

7 - все файлы, где упоминается последовательность boost::asio 
$grep -rL "boost::asio"
![image](https://user-images.githubusercontent.com/56314346/157692727-3f9dba99-d316-42f5-80a7-f53e8f3207c3.png)

8 - компилируем буст 
$./bootstrap.sh
$./b2

 9 - Перенос всех скомпилированных на предыдущем шаге статических библиотек в директорию ~/boost-libs.
$mv stage/lib/ ~/boost-libs

10 - подсчет занятого пространства на диске 
$ du -a
![image](https://user-images.githubusercontent.com/56314346/157693602-8c5f9579-8427-4363-afcf-a3603794d4da.png)

11 - топ 10 самый тяжелых файлов 
$ du -ahx . | sort -rh | head -10
