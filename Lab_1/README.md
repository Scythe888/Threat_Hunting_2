Информационно-аналитические технологии поиска угроз информационной
безопасности
================
Vinnitskij Vlad

Лабораторная работа 1

## Цель

Пройти 4 урока по R Programming в swirl

## Исходные данные

1.  ОС Windows 10
2.  RStudio Desktop
3.  Интерпретатор языка R 4.3.2
4.  Swirl

## План

1.  Установить пакет swirl
2.  Запустить в консоли swirl::swirl()
3.  Пройти 4 урока

## Шаги

### Установка swirl

Пакет swirl можно установить в RStudio Desktop с помощью команды
install.packages(“swirl”) После успешной установки в консоли пишем
команду swirl::swirl() и начинаем прохождение уроков.

### 1. Basic Building Blocks

In its simplest form, R can be used as an interactive calculator. Type
5 + 7 and press Enter.

В самой простой форме R может использоваться как интерактивный
калькулятор. Введите 5 + 7 и нажмите Enter.

``` r
5 + 7
```

    [1] 12

To assign the result of 5 + 7 to a new variable called x, you type x \<-
5 + 7. This can be read as ‘x gets 5 plus 7’. Give it a try now. To view
the contents of the variable x, just type x and press Enter. Try it now.

Чтобы присвоить результат 5 + 7 новой переменной с именем x, введите x
\<- 5 + 7. Это можно интерпретировать как ‘x получает 5 плюс 7’.
Попробуйте сейчас. Чтобы посмотреть содержимое переменной x, просто
введите x и нажмите Enter. Попробуйте сейчас.

``` r
x <- 5 + 7
x
```

    [1] 12

Now, store the result of x - 3 in a new variable called y. What is the
value of y? Type y to find out.

Теперь сохраните результат x - 3 в новой переменной с именем y. Каково
значение y? Введите y, чтобы узнать.

``` r
y <- x - 3
y
```

    [1] 9

The easiest way to create a vector is with the c() function, which
stands for ‘concatenate’ or ‘combine’. To create a vector containing the
numbers 1.1, 9, and 3.14, type c(1.1, 9, 3.14). Try it now and store the
result in a variable called z.

Самый простой способ создать вектор - использовать функцию c(), которая
означает ‘конкатенация’ или ‘комбинирование’. Чтобы создать вектор,
содержащий числа 1.1, 9 и 3.14, введите c(1.1, 9, 3.14). Попробуйте
сейчас и сохраните результат в переменной с именем z.

``` r
z <- c(1.1, 9, 3.14)
z
```

    [1] 1.10 9.00 3.14

Type ?c and press Enter. This will bring up the help file for the c()
function. Type z to view its contents. Notice that there are no commas
separating the values in the output.

Введите ?c и нажмите Enter. Это вызовет справку для функции c(). Введите
z, чтобы посмотреть ее содержимое. Обратите внимание, что между
значениями в выводе нет запятых.

``` r
?c
```

    запускаю httpd сервер помощи... готово

You can combine vectors to make a new vector. Create a new vector that
contains z, 555, then z again in that order. Don’t assign this vector to
a new variable, so that we can just see the result immediately.

Вы можете объединить векторы, чтобы создать новый вектор. Создайте новый
вектор, содержащий z, 555, затем снова z в этом порядке. Не присваивайте
этот вектор новой переменной, чтобы мы могли сразу увидеть результат.

``` r
c(z, 555, z)
```

    [1]   1.10   9.00   3.14 555.00   1.10   9.00   3.14

Numeric vectors can be used in arithmetic expressions. Type the
following to see what happens: z \* 2 + 100.

Числовые векторы можно использовать в арифметических выражениях. Введите
следующее, чтобы увидеть, что произойдет: z \* 2 + 100.

``` r
z * 2 + 100
```

    [1] 102.20 118.00 106.28

Take the square root of z - 1 and assign it to a new variable called
my_sqrt.

Возьмите квадратный корень из z - 1 и присвойте его новой переменной с
именем my_sqrt.

``` r
my_sqrt <- sqrt(z - 1)
my_sqrt
```

    [1] 0.3162278 2.8284271 1.4628739

Now, create a new variable called my_div that gets the value of z
divided by my_sqrt.

Теперь создайте новую переменную с именем my_div, которая получает
значение z деленное на my_sqrt.

``` r
my_div <- z / my_sqrt
my_div
```

    [1] 3.478505 3.181981 2.146460

To see another example of how this vector ‘recycling’ works, try adding
c(1, 2, 3, 4) and c(0, 10). Don’t worry about saving the result in a new
variable.

Чтобы увидеть еще один пример того, как работает ‘рециклинг’ вектора,
попробуйте сложить c(1, 2, 3, 4) и c(0, 10). Не беспокойтесь о
сохранении результата в новую переменную.

``` r
c(1, 2, 3, 4) + c(0, 10)
```

    [1]  1 12  3 14

Try c(1, 2, 3, 4) + c(0, 10, 100) for an example.

Попробуйте c(1, 2, 3, 4) + c(0, 10, 100) для примера.

``` r
c(1, 2, 3, 4) + c(0, 10, 100)
```

    Warning in c(1, 2, 3, 4) + c(0, 10, 100): длина большего объекта не является
    произведением длины меньшего объекта

    [1]   1  12 103   4

In many programming environments, the up arrow will cycle through
previous commands. Try hitting the up arrow on your keyboard until you
get to this command (z \* 2 + 100), then change 100 to 1000 and hit
Enter. If the up arrow doesn’t work for you, just type the corrected
command.

Во многих средах программирования стрелка вверх циклически просматривает
предыдущие команды. Попробуйте нажать стрелку вверх на клавиатуре, пока
не дойдете до этой команды (z \* 2 + 100), затем измените 100 на 1000 и
нажмите Enter. Если стрелка вверх для вас не работает, просто введите
исправленную команду.

``` r
z * 2 + 1000
```

    [1] 1002.20 1018.00 1006.28

### 2. Workspace and Files

Determine which directory your R session is using as its current working
directory using getwd().

Определите, какая директория используется вашей сессией R в качестве
текущей рабочей директории, используя getwd().

``` r
getwd()
```

    [1] "D:/Rstudio_Projects/Lab_1"

List all the objects in your local workspace using ls().

Выведите все объекты в вашем локальном рабочем пространстве с помощью
ls().

``` r
ls()
```

    [1] "my_div"  "my_sqrt" "x"       "y"       "z"      

Assign 9 to x using x \<- 9.

Присвойте переменной x значение 9, используя x \<- 9.

``` r
x <- 9
```

Now take a look at objects that are in your workspace using ls().

Теперь посмотрите на объекты, находящиеся в вашем рабочем пространстве,
снова используя ls().

``` r
ls()
```

    [1] "my_div"  "my_sqrt" "x"       "y"       "z"      

List all the files in your working directory using list.files()

Выведите все файлы в вашей рабочей директории с помощью list.files().

``` r
list.files()
```

    [1] "_quarto.yml"     "Lab_1.qmd"       "Lab_1.rmarkdown" "Lab_1.Rproj"    
    [5] "mytest2.R"       "mytest3.R"       "README.md"       "testdir"        
    [9] "testdir2"       

or dir().

или dir().

``` r
dir()
```

    [1] "_quarto.yml"     "Lab_1.qmd"       "Lab_1.rmarkdown" "Lab_1.Rproj"    
    [5] "mytest2.R"       "mytest3.R"       "README.md"       "testdir"        
    [9] "testdir2"       

As we go through this lesson, you should be examining the help page for
each new function. Check out the help page for list.files with the
command ?list.files.

Во время выполнения этого урока вы должны изучить справку для каждой
новой функции. Ознакомьтесь со справкой для функции list.files с помощью
команды ?list.files.

``` r
?list.files
```

Using the args() function on a function name is also a handy way to see
what arguments a function can take.

Использование функции args() для имени функции также удобный способ
увидеть, какие аргументы может принимать функция.

``` r
args(list.files)
```

    function (path = ".", pattern = NULL, all.files = FALSE, full.names = FALSE, 
        recursive = FALSE, ignore.case = FALSE, include.dirs = FALSE, 
        no.. = FALSE) 
    NULL

Assign the value of the current working directory to a variable called
“old.dir”.

Присвойте значение текущей рабочей директории переменной с именем
“old.dir”.

``` r
old.dir <- getwd()
```

Use dir.create() to create a directory in the current working directory
called “testdir”.

Используйте dir.create(), чтобы создать директорию в текущей рабочей
директории с именем “testdir”.

``` r
dir.create("testdir")
```

    Warning in dir.create("testdir"): 'testdir' уже существует

Set your working directory to “testdir” with the setwd() command.

Установите вашу рабочую директорию в “testdir” с помощью команды
setwd().

``` r
setwd("testdir")
```

Create a file in your working directory called “mytest.R” using the
file.create() function.

Создайте файл в вашей рабочей директории с именем “mytest.R” с помощью
функции file.create().

``` r
file.create("mytest.R")
```

    [1] TRUE

This should be the only file in this newly created directory. Let’s
check this by listing all the files in the current directory.

Это должен быть единственный файл в этой новой созданной директории.
Давайте проверим это, выведя все файлы в текущей директории.

``` r
list.files()
```

     [1] "_quarto.yml"     "Lab_1.qmd"       "Lab_1.rmarkdown" "Lab_1.Rproj"    
     [5] "mytest.R"        "mytest2.R"       "mytest3.R"       "README.md"      
     [9] "testdir"         "testdir2"       

Check to see if “mytest.R” exists in the working directory using the
file.exists() function.

Проверьте, существует ли “mytest.R” в рабочей директории с помощью
функции file.exists().

``` r
file.exists("mytest.R")
```

    [1] TRUE

Access information about the file “mytest.R” by using file.info().

Получите информацию о файле “mytest.R”, используя функцию file.info().

``` r
file.info("mytest.R")
```

             size isdir mode               mtime               ctime
    mytest.R    0 FALSE  666 2023-12-20 18:53:53 2023-12-20 18:53:53
                           atime exe
    mytest.R 2023-12-20 18:53:53  no

Change the name of the file “mytest.R” to “mytest2.R” by using
file.rename().

Измените имя файла “mytest.R” на “mytest2.R” с использованием функции
file.rename().

``` r
file.rename("mytest.R", "mytest2.R")
```

    [1] TRUE

Make a copy of “mytest2.R” called “mytest3.R” using file.copy().

Сделайте копию “mytest2.R” с именем “mytest3.R” с использованием функции
file.copy().

``` r
file.copy("mytest2.R", "mytest3.R")
```

    [1] FALSE

Provide the relative path to the file “mytest3.R” by using file.path().

Укажите относительный путь к файлу “mytest3.R”, используя функцию
file.path().

``` r
file.path("mytest3.R")
```

    [1] "mytest3.R"

You can use file.path to construct file and directory paths that are
independent of the operating system your R code is running on. Pass
‘folder1’ and ‘folder2’ as arguments to file.path to make a
platform-independent pathname.

Можно использовать file.path для создания файловых и каталожных путей,
которые не зависят от операционной системы, на которой выполняется ваш
код R. Передайте ‘folder1’ и ‘folder2’ в качестве аргументов в
file.path, чтобы создать платформо-независимый путь.

``` r
file.path("folder1", "folder2")
```

    [1] "folder1/folder2"

Create a directory in the current working directory called “testdir2”
and a subdirectory for it called “testdir3”, all in one command by using
dir.create() and file.path().

Создайте директорию в текущей рабочей директории с именем “testdir2” и
поддиректорию для нее с именем “testdir3”, все в одной команде с
использованием dir.create() и file.path().

``` r
dir.create(file.path('testdir2', 'testdir3'), recursive = TRUE)
```

    Warning in dir.create(file.path("testdir2", "testdir3"), recursive = TRUE):
    'testdir2\testdir3' уже существует

Go back to your original working directory using setwd(). (Recall that
we created the variable old.dir with the full path for the orginal
working directory at the start of these questions.)

Вернитесь к вашей первоначальной рабочей директории с помощью setwd().
(Напомним, что мы создали переменную old.dir с полным путем к исходной
рабочей директории в начале этих вопросов.)

``` r
setwd(old.dir)
```

### 3. Sequences of Numbers

The simplest way to create a sequence of numbers in R is by using the
`:` operator. Type 1:20 to see how it works.

Самый простой способ создать последовательность чисел в R - использовать
оператор `:`. Введите 1:20, чтобы увидеть, как это работает.

``` r
1:20
```

     [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20

That gave us every integer between (and including) 1 and 20. We could
also use it to create a sequence of real numbers. For example, try
pi:10.

Это дало нам все целые числа от 1 до 20 включительно. Мы также можем
использовать его для создания последовательности действительных чисел.
Например, попробуйте pi:10.

``` r
pi:10
```

    [1] 3.141593 4.141593 5.141593 6.141593 7.141593 8.141593 9.141593

What happens if we do 15:1? Give it a try to find out.

Что произойдет, если мы сделаем 15:1? Давайте попробуем, чтобы узнать.

``` r
15:1
```

     [1] 15 14 13 12 11 10  9  8  7  6  5  4  3  2  1

Remember that if you have questions about a particular R function, you
can access its documentation with a question mark followed by the
function name: ?function_name_here. However, in the case of an operator
like the colon used above, you must enclose the symbol in backticks like
this: ?`:`. (NOTE: The backtick (\`) key is generally located in the top
left corner of a keyboard, above the Tab key. If you don’t have a
backtick key, you can use regular quotes.)

Помните, что если у вас есть вопросы по поводу конкретной функции R, вы
можете получить доступ к ее документации с помощью вопросительного
знака, за которым следует имя функции: ?название_функции_здесь. Однако в
случае оператора, такого как двоеточие, использованного выше, вы должны
заключить символ в обратные кавычки, как здесь:
?:`. (ПРИМЕЧАНИЕ: Клавиша обратной кавычки (\`) обычно расположена в
верхнем левом углу клавиатуры, над клавишей Tab. Если у вас нет клавиши
обратной кавычки, вы можете использовать обычные кавычки.)

``` r
?':'
```

The most basic use of seq() does exactly the same thing as the `:`
operator. Try seq(1, 20) to see this.

Наиболее базовый способ использования функции seq() делает то же самое,
что и оператор :. Попробуйте seq(1, 20), чтобы увидеть это.

``` r
seq(1, 20)
```

     [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20

This gives us the same output as 1:20. However, let’s say that instead
we want a vector of numbers ranging from 0 to 10, incremented by 0.5.
seq(0, 10, by=0.5) does just that. Try it out.

Это дает нам тот же результат, что и 1:20. Однако предположим, что
вместо этого мы хотим вектор чисел от 0 до 10 с шагом 0,5. seq(0, 10,
by=0.5) делает это. Попробуйте сейчас и сохраните результат в новую
переменную с именем my_seq.

``` r
seq(0, 10, by=0.5)
```

     [1]  0.0  0.5  1.0  1.5  2.0  2.5  3.0  3.5  4.0  4.5  5.0  5.5  6.0  6.5  7.0
    [16]  7.5  8.0  8.5  9.0  9.5 10.0

Or maybe we don’t care what the increment is and we just want a sequence
of 30 numbers between 5 and 10. seq(5, 10, length=30) does the trick.
Give it a shot now and store the result in a new variable called my_seq.

``` r
my_seq <- seq(5, 10, length=30)
```

To confirm that my_seq has length 30, we can use the length() function.
Try it now.

Чтобы подтвердить, что у my_seq длина 30, мы можем использовать функцию
length(). Попробуйте сейчас.

``` r
length(my_seq)
```

    [1] 30

There are several ways we could do this. One possibility is to combine
the `:` operator and the length() function like this: 1:length(my_seq).
Give that a try.

Есть несколько способов сделать это. Один из вариантов - объединить
оператор `:` и функцию length() следующим образом: 1:length(my_seq).
Попробуйте это.

``` r
1:length(my_seq)
```

     [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
    [26] 26 27 28 29 30

Another option is to use seq(along.with = my_seq). Give that a try.

Еще один вариант - использовать seq(along.with = my_seq). Попробуйте
это.

``` r
seq(along.with = my_seq)
```

     [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
    [26] 26 27 28 29 30

However, as is the case with many common tasks, R has a separate
built-in function for this purpose called seq_along(). Type
seq_along(my_seq) to see it in action.

Однако, как и во многих обычных задачах, в R есть отдельная встроенная
функция для этой цели, называемая seq_along(). Введите
seq_along(my_seq), чтобы увидеть ее в действии.

``` r
seq_along(my_seq)
```

     [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
    [26] 26 27 28 29 30

If we’re interested in creating a vector that contains 40 zeros, we can
use rep(0, times = 40). Try it out.

Если мы хотим создать вектор, содержащий 40 нулей, мы можем использовать
rep(0, times = 40). Попробуйте сейчас.

``` r
rep(0, times = 40)
```

     [1] 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0
    [39] 0 0

If instead we want our vector to contain 10 repetitions of the vector
(0, 1, 2), we can do rep(c(0, 1, 2), times = 10). Go ahead.

Если вместо этого мы хотим, чтобы наш вектор содержал 10 повторений
вектора (0, 1, 2), мы можем использовать rep(c(0, 1, 2), times = 10).
Продолжайте.

``` r
rep(c(0, 1, 2), times = 10)
```

     [1] 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2

Finally, let’s say that rather than repeating the vector (0, 1, 2) over
and over again, we want our vector to contain 10 zeros, then 10 ones,
then 10 twos. We can do this with the `each` argument. Try rep(c(0, 1,
2), each = 10).

Наконец, предположим, что вместо повторения вектора (0, 1, 2) снова и
снова, мы хотим, чтобы наш вектор содержал 10 нулей, затем 10 единиц,
затем 10 двоек. Мы можем сделать это с аргументом each. Попробуйте
rep(c(0, 1, 2), each = 10).

``` r
rep(c(0, 1, 2), each = 10)
```

     [1] 0 0 0 0 0 0 0 0 0 0 1 1 1 1 1 1 1 1 1 1 2 2 2 2 2 2 2 2 2 2

### 4. Vectors

First, create a numeric vector num_vect that contains the values 0.5,
55, -10, and 6.

Сначала создайте числовой вектор num_vect, который содержит значения
0.5, 55, -10 и 6.

``` r
num_vect <- c(0.5, 55, -10, 6)
```

Now, create a variable called tf that gets the result of num_vect \< 1,
which is read as ‘num_vect is less than 1’.

Теперь создайте переменную с именем tf, которая получает результат
num_vect \< 1, что читается как ‘num_vect меньше 1’.

``` r
tf <- num_vect < 1
tf
```

    [1]  TRUE FALSE  TRUE FALSE

Let’s try another. Type num_vect \>= 6 without assigning the result to a
new variable.

Давайте попробуем еще один. Введите num_vect \>= 6, не присваивая
результат новой переменной.

``` r
num_vect >= 6
```

    [1] FALSE  TRUE FALSE  TRUE

Create a character vector that contains the following words: “My”,
“name”, “is”. Remember to enclose each word in its own set of double
quotes, so that R knows they are character strings. Store the vector in
a variable called my_char.

Создайте символьный вектор, который содержит следующие слова: “Мой”,
“имя”, “Георгий”. Не забудьте заключить каждое слово в свои собственные
кавычки, чтобы R знал, что это символьные строки. Сохраните вектор в
переменную с именем my_char.

``` r
my_char <- c("My", "name", "is")
my_char
```

    [1] "My"   "name" "is"  

Type paste(my_char, collapse = ” “) now. Make sure there’s a space
between the double quotes in the `collapse` argument. You’ll see why in
a second.

Теперь введите paste(my_char, collapse = ” “). Убедитесь, что между
кавычками в аргументе collapse есть пробел. Вы увидите почему в
следующем шаге.

``` r
paste(my_char, collapse = " ")
```

    [1] "My name is"

To add (or ‘concatenate’) your name to the end of my_char, use the c()
function like this: c(my_char, “your_name_here”). Place your name in
double quotes where I’ve put “your_name_here”. Try it now, storing the
result in a new variable called my_name.

Чтобы добавить (или ‘конкатенировать’) свое имя в конец my_char,
используйте функцию c() так: c(my_char, “ваше_имя_здесь”). Поместите
свое имя в кавычки там, где у меня “ваше_имя_здесь”. Попробуйте это
сейчас, сохраняя результат в новую переменную с именем my_name.

``` r
my_name <- c(my_char, "Georgy")
my_name
```

    [1] "My"     "name"   "is"     "Georgy"

Now, use the paste() function once more to join the words in my_name
together into a single character string. Don’t forget to say collapse =
” “!

Теперь используйте функцию paste() еще раз, чтобы объединить слова в
my_name в единый символьный строку. Не забудьте указать collapse = ” “!

``` r
paste(my_name, collapse = " ")
```

    [1] "My name is Georgy"

In the simplest case, we can join two character vectors that are each of
length 1 (i.e. join two words). Try paste(“Hello”,“world!”, sep = ” “),
where the `sep` argument tells R that we want to separate the joined
elements with a single space.

В самом простом случае мы можем объединить два символьных вектора,
каждый длиной 1 (т.е. объединить два слова). Попробуйте paste(“Привет”,
“мир!”, sep = ” “), где аргумент sep сообщает R, что мы хотим разделять
объединенные элементы одним пробелом.

``` r
paste("Hello", "world!", sep = " ")
```

    [1] "Hello world!"

For a slightly more complicated example, we can join two vectors, each
of length 3. Use paste() to join the integer vector 1:3 with the
character vector c(“X”, “Y”, “Z”). This time, use sep = “” to leave no
space between the joined elements.

Для слегка более сложного примера мы можем объединить два вектора,
каждый длиной 3. Используйте paste(), чтобы объединить целочисленный
вектор 1:3 с символьным вектором c(“X”, “Y”, “Z”). На этот раз
используйте sep = ““, чтобы не оставлять пробела между объединенными
элементами.

``` r
paste(1:3, c("X", "Y", "Z"), sep = "")
```

    [1] "1X" "2Y" "3Z"

``` r
paste(LETTERS, 1:4, sep = "-")
```

     [1] "A-1" "B-2" "C-3" "D-4" "E-1" "F-2" "G-3" "H-4" "I-1" "J-2" "K-3" "L-4"
    [13] "M-1" "N-2" "O-3" "P-4" "Q-1" "R-2" "S-3" "T-4" "U-1" "V-2" "W-3" "X-4"
    [25] "Y-1" "Z-2"

## Оценка результата

В результате лабораторной работы мы прошли 4 урока по языку
программирования R, тем самым разобравшись в базовых аспектах языка.

## Вывод

Мы получили базовые навыки работы с RStudio Desktop и языком R
