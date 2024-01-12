___
# МИНИСТЕРСТВО НАУКИ И ВЫСШЕГО ОБРАЗОВАНИЯ РОССИЙСКОЙ ФЕДЕРАЦИИ ФЕДЕРАЛЬНОЕ ГОСУДАРСТВЕННОЕ БЮДЖЕТНОЕ ОБРАЗОВАТЕЛЬНОЕ УЧРЕЖДЕНИЕ ВЫСШЕГО ПРОФЕСИОНАЛЬНОГО ОБРАЗОВАНИЯ «САХАЛИНСКИЙ ГОСУДАРСТВЕННЫЙ УНИВЕРСИТЕТ»
### <p align="center">Лабораторная работа №10 «JavaScript».</p> 
#### <br><p align="right">Подготовил студент направления подготовки 01.03.02 «Прикладная математика и информатика»<br> Института естественных наук и техносферной безопасности<br> Зураев Дмитрий Бакенович.</p><br><p align="right">Научный руководитель:<br> Соболев Евгений Игоревич</p><br> <p align="center">Южно-Сахалинск 2023 г.</p>
___
### <p align="center">Введение</p>
<p align="justify"> <b>JavaScript</b> является одним из самых популярных языков программирования, применяемых веб-разработкой. Он обладает мощными возможностями для работы с функциями, что делает его незаменимым инструментом для создания интерактивных и динамических веб-приложений.
</p>

### <p align="center">Цели</p>
<p align="justify">Ознакомиться с основными концепциями и возможностями JavaScript в области работы с функциями. Функции в JavaScript являются одним из ключевых строительных блоков языка, позволяющих организовывать код в модули и повторно использовать его.</p>

### <p align="center">Задачи</p>
<p align="justify">Применить технологию JS.</p>

____________________
## <p align="center">_Решение_</p>

1. Напишите функцию, которая найдёт числа в массиве, которые делятся на заданное число.
```javascript
 function findNumInArray(arr, num){ 
    var newNumsArr = [];
    for(let i = 0; i < arr.length; i++){
        if(arr[i] % num == 0)
            newNumsArr.push(arr[i]);
    }
    if(newNumsArr.length != 0)
        alert(newNumsArr);
    else   
        alert('Нет таких элементов');    
}
```
2. Нужно написать функцию, которая проверяет, являются ли две строки анаграммами, причем регистр букв не имеет значения. Учитываются лишь символы; пробелы или знаки препинания в расчет не берутся.
```javascript
function isAnagram(str1, str2) {
    str1 = str1.toLowerCase();
    str2 = str2.toLowerCase();
    str1 = str1.replaceAll(' ', '');
    str2 = str2.replaceAll(' ', '');
            
    var sortedStr1 = str1.split('').sort().join('');
    var sortedStr2 = str2.split('').sort().join('');

    if (sortedStr1 == sortedStr2) {
        alert("Строки являются анаграммами");
    } else {
        alert("Строки не являются анаграммами");
    }
}
```
3. Нужно написать функцию, принимающую строку в качестве аргумента и возвращающую количество гласных, которые содержатся в строке.
Гласными являются «a», «e», «i», «o», «u».
```javascript
function countVowels(str)
{
    let count = 0;
    let glasn = 'aeiou'
    for (let i = 0; i < str.length; i++)
        if (glasn.includes(str[i])) count++;
    return count;
}
```
4. Треугольник. Напишите цикл,  выводит такой треугольник:<br>
1 #<br>
2 ##<br>
3 ###<br>
4 ####<br>
5 #####<br>
6 ######<br>
7 #######
```javascript
 function writeGrid(){
    var str = '#'; 
    for(let i = 1; i <= 7; i++){
        document.write(i + '.\t' + str + '<br>');
        str += '#';
    }
}
```
5. FizzBuzz. Напишите программу, которая выводит через `console.log` все числа от 1 до 100, с двумя исключениями. Для чисел, нацело делящихся на 3, она должна выводить ‘Fizz’, а для чисел, делящихся на 5 (но не на 3) – ‘Buzz’.Когда сумеете – исправьте её так, чтобы она выводила «FizzBuzz» для всех чисел, которые делятся и на 3 и на 5.
```javascript
function FizzOrBuzz() {
    for (let i = 1; i <= 100; i++) {
        if(i % 3 == 0)
        {
            console.log('Fizz');
            continue;
        }
        else if (i % 5 == 0 && i % 3 != 0)
        {
            console.log('Buzz');
            continue;
        }
        console.log(i);
    }
}

function FizzBuzz() {
    for (let i = 1; i <= 100; i++) {
        if (i % 5 == 0 && i % 3 == 0)
        {
            console.log('FuzzBuzz');
            continue;
        }
        console.log(i);
    } 
}
```
6. Шахматная доска. Напишите программу, создающую строку, содержащую решётку 8х8, в которой линии разделяются символами новой строки. На каждой позиции либо пробел, либо #.
```javascript 
//b - black, w - white
function createChessBoard() {
    var chessBoard = '';
    for(let i = 1; i <= 8; i++){
        for(let j = 1; j <= 8; j++){
            if(i % 2 == 0){
                if(j % 2 == 0)
                    chessBoard+='w'; 
                else    
                    chessBoard+='b';
            } else {
                if(j % 2 == 0)
                    chessBoard+='b';
                else    
                    chessBoard+='w'; 
            }
        }
        chessBoard+='<br>';
    }

    document.write(chessBoard);
}
```
7. Минимум. Напишите функцию `min`, принимающую два аргумента, и возвращающую минимальный из них.
```javascript 
function min(a,b){
    if(a<b)
        return a;
    else
        return b;
}
```
8. Рекурсия. Ноль чётный. Единица нечётная. У любого числа N чётность такая же, как у N-2. Напишите рекурсивную функцию isEven согласно этим правилам. Она должна принимать число и возвращать булевское значение. Потестируйте её на 50 и 75. Попробуйте задать ей -1. Почему она ведёт себя таким образом? Можно ли её как-то исправить?
```javascript
function isEven(n){
    if(n == 0) return true;
    if(n == 1) return false;
    if(n < 0) return false;
    return isEven(n-2);
}
```
9. Считаем бобы. Символ номер `N` строки можно получить, добавив к ней `.charAt(N)` ( `“строчка”.charAt(5)` ) – схожим образом с получением длины строки при помощи `.length`. Возвращаемое значение будет строковым, состоящим из одного символа (к примеру, “к”). У первого символа строки позиция 0, что означает, что у последнего символа позиция будет `string.length – 1`. Другими словами, у строки из двух символов длина 2, а позиции её символов будут 0 и 1.Напишите функцию `countBs`, которая принимает строку в качестве аргумента, и возвращает количество символов “B”, содержащихся в строке. Затем напишите функцию `countChar`, которая работает примерно как `countBs`, только принимает второй параметр — символ, который мы будем искать в строке (вместо того, чтобы просто считать количество символов “B”). Для этого переделайте функцию `countBs`.
```javascript
function countBs(str){
    var count = 0;
    for (let i = 0; i <= str.length; i++)
    {
        if (str[i] == 'B') 
            count++;
    }
    return count;
}
function countChar(str,symbol)
{
    var count = 0;
    for (let i = 0; i <= str.length; i++)
    {
        if (str[i] == symbol) 
            count++;
    }
    return count;
}
```
10. Сумма диапазона. Напишите функцию `range`, принимающую два аргумента, начало и конец диапазона, и возвращающую массив, который содержит все числа из него, включая начальное и конечное. Затем напишите функцию `sum`, принимающую массив чисел и возвращающую их сумму. Запустите указанную выше инструкцию и убедитесь, что она возвращает 55.В качестве бонуса дополните функцию `range`, чтобы она могла принимать необязательный третий аргумент – шаг для построения массива. Если он не задан, шаг равен единице. Вызов функции `range(1, 10, 2)` должен будет вернуть [1, 3, 5, 7, 9]. Убедитесь, что она работает с отрицательным шагом так, что вызов `range(5, 2, -1)` возвращает [5, 4, 3, 2].
```javascript
function range(beginning, end, step = 1)
{
    let resultArr = [];
    let count = 0;
    if (step < 0)
    {
        beginning *= -1;
        end *= -1;
        step *= -1;
    }
    for(let i = beginning; i <= end; i += step)
    {
        resultArr[count] = Math.abs(i);
        count++;
    }
    return resultArr;          
}

function sum(arr)
{
    let sumOfNums = 0;
    for(let i = 0; i < arr.length; i++)
    {
        sumOfNums += arr[i];
    }
    return sumOfNums;
}
```
11. Обращаем массив вспять. Напишите две функции, `reverseArray` и `reverseArrayInPlace`. Первая получает массив как аргумент и выдаёт новый массив, с обратным порядком элементов. Вторая работает как оригинальный метод reverse – она меняет порядок элементов на обратный в том массиве, который был ей передан в качестве аргумента. Не используйте стандартный метод `reverse`.
```javascript
function reverseArray(arr){
    let res = [];
    for(let i = 0; i < arr.length; i++)
        res[i] = arr[arr.length - 1 - i];
            
    return res;
}
function reverseArrayInPlace(arr)
{
    for(let i = 0; i < arr.length; i++)
        arr[i] = arr[arr.length - 1 - i];
    return;
}
```
12.	Глубокое сравнение. Оператор `==` сравнивает переменные объектов, проверяя, ссылаются ли они на один объект. Но иногда полезно было бы сравнить объекты по содержимому. Напишите функцию `deepEqual`, которая принимает два значения и возвращает `true`, только если это два одинаковых значения или это объекты, свойства которых имеют одинаковые значения, если их сравнивать рекурсивным вызовом `deepEqual`. Чтобы узнать, когда сравнивать величины через `===`, а когда – объекты по содержимому, используйте оператор `typeof`. Если он выдаёт “object” для обеих величин, значит нужно делать глубокое сравнение. Не забудьте об одном дурацком исключении, случившемся из-за исторических причин: “typeof null” тоже возвращает “object”.
```javascript
function deepEqual(value1, value2) {
    if(typeof(value1) != 'object' && typeof(value2) != 'object') 
        return value1 === value2;
    if(value1 == null && value2 == null) 
        return true;
    if(value1 == null || value2 == null) 
        return false;

    let keys1 = Object.keys(value1);
    let keys2 = Object.keys(value2);
            
    if(keys1.length != keys2.length) 
        return false;

    for(key of keys1)
        if(!keys2.includes(key) || !deepEqual(value1[key], value2[key])) 
            return false;
            
    return true;
}
```
13.	Свертка. Используйте метод `reduce` в комбинации с `concat` для свёртки массива массивов в один массив, у которого есть все элементы входных массивов.
```javascript
function thirteen(){
    const arrays = [
        [1, 2, 3], 
        [4, 5], 
        [6]
    ];

    const collapsedArray = arrays.reduce((accumulator, currentArray) => {
        return accumulator.concat(currentArray);
    }, []);

    console.log(collapsedArray);
}
```
### Файл index.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lab10</title>
    <link href="style.css" rel="stylesheet">
</head>
<body>
    <script>
        function clearC(){
            console.clear();
        } 
        //1
        function findNumInArray(arr, num){ 
            var newNumsArr = [];
            for(let i = 0; i < arr.length; i++){
                if(arr[i] % num == 0)
                    newNumsArr.push(arr[i]);
            }
            if(newNumsArr.length != 0)
                alert(newNumsArr);
            else   
                alert('Нет таких элементов');    
        }

        function one(){
            var myArray = [4, 16, 7, 9, 8, -4];
            var num = prompt(`Введите число, а я найду числа в массиве ${myArray}, которые  делятся на заданное цисло: `);
            findNumInArray(myArray, num);
        }
        //2
        function isAnagram(str1, str2) {
            str1 = str1.toLowerCase();
            str2 = str2.toLowerCase();
            str1 = str1.replaceAll(' ', '');
            str2 = str2.replaceAll(' ', '');
            
            var sortedStr1 = str1.split('').sort().join('');
            var sortedStr2 = str2.split('').sort().join('');

            if (sortedStr1 == sortedStr2) {
                alert("Строки являются анаграммами");
            } else {
                alert("Строки не являются анаграммами");
            }
        }
        
        function two(){
            var str1 = prompt(`Проверка на анаграмму. Введите первую строку: `);
            var str2 = prompt(`Проверка на анаграмму. Введите вторую строку: `);
            isAnagram(str1, str2);
        }
        //3
        function countVowels(str)
        {
            let count = 0;
            let glasn = 'aeiou'
            for (let i = 0; i < str.length; i++)
                if (glasn.includes(str[i])) count++;
            return count;
        }

        function three(){
            var str = "Do they win?";
            alert(`Количество гласных aeiou в строке ${str} = ` + countVowels(str));
        }
        //4
        function writeGrid(){
            var str = '#'; 
            for(let i = 1; i <= 7; i++){
                document.write(i + '.\t' + str + '<br>');
                str += '#';
            }
        }
        //5
        function FizzOrBuzz() {
            for (let i = 1; i <= 100; i++) {
                if(i % 3 == 0)
                {
                    console.log('Fizz');
                    continue;
                }
                else if (i % 5 == 0 && i % 3 != 0)
                {
                    console.log('Buzz');
                    continue;
                }
                console.log(i);
            }
        }
        function FizzBuzz() {
            for (let i = 1; i <= 100; i++) {
                if (i % 5 == 0 && i % 3 == 0)
                {
                    console.log('FuzzBuzz');
                    continue;
                }
                console.log(i);
            } 
        }
        //6
        function createChessBoard() {
            var chessBoard = '';
            for(let i = 1; i <= 8; i++){
                for(let j = 1; j <= 8; j++){
                    if(i % 2 == 0){
                        if(j % 2 == 0)
                            chessBoard+='w'; 
                        else    
                            chessBoard+='b';
                    } else {
                        if(j % 2 == 0)
                            chessBoard+='b';
                        else    
                            chessBoard+='w'; 
                    }
                }
                chessBoard+='<br>';
            }

            document.write(chessBoard);
        }
        //7
        function min(a,b){
            if(a<b)
                return a;
            else
                return b;
        }

        function seven(){
            var a = prompt('Введите два числа, я выведу минимальное из них\n\nПервое число: ');
            var b = prompt('Введите два числа, я выведу минимальное из них\n\nВторое число: ');
            alert(`Из двух чисел ${a} и ${b}, минимальное ${min(a,b)}`);
            //alert(min(-2,-5));
        }
        //8
        function isEven(n){
            if(n == 0) return true;
            if(n == 1) return false;
            if(n < 0) return false;
            return isEven(n-2);
        }

        function eight(){
            alert("Четное ли число 50?\n" + isEven(50));
            alert("Четное ли число 75?\n" + isEven(75));
            console.log("Четное ли число -1?\n" + isEven(-1));
        }
        //9
        function countBs(str){
            var count = 0;
            for (let i = 0; i <= str.length; i++)
            {
                if (str[i] == 'B') 
                    count++;
            }
            return count;
        }
        function countChar(str,symbol)
        {
            var count = 0;
            for (let i = 0; i <= str.length; i++)
            {
                if (str[i] == symbol) 
                    count++;
            }
            return count;
        }
        function nine(){
            var str = 'BIG RUSSIAN BOSS';
            alert(`Количество символов B в строке ${str} = ${countBs(str)}`);

            var str2 = 'BIG RUSSIAN BOSS';
            var symbol = 'S';
            alert(`Количество символов ${symbol} в строке ${str} = ${countChar(str2, symbol)}`);
        }

        //10
        function range(beginning, end, step = 1)
        {
            let resultArr = [];
            let count = 0;
            if (step < 0)
            {
                beginning *= -1;
                end *= -1;
                step *= -1;
            }
            for(let i = beginning; i <= end; i += step)
            {
                resultArr[count] = Math.abs(i);
                count++;
            }
            return resultArr;          
        }
        function sum(arr)
        {
            let sumOfNums = 0;
            for(let i = 0; i < arr.length; i++)
            {
                sumOfNums += arr[i];
            }
            return sumOfNums;
        }
        
        function ten(){
            myArray = range(5, 2, -1);
            for(let i = 0; i < myArray.length; i++)
            {
                console.log(myArray[i]);
            }
            console.log("Сумма чисел массива: " + sum(myArray));
        }
        //11
        function reverseArray(arr){
            let res = [];
            for(let i = 0; i < arr.length; i++)
                res[i] = arr[arr.length - 1 - i];
            
            return res;
        }
        function reverseArrayInPlace(arr)
        {
            for(let i = 0; i < arr.length; i++)
                arr[i] = arr[arr.length - 1 - i];
            return;
        }
        function printArray(arr)
        {
            let myArray = "";
            for(let i = 0; i < arr.length; i++)
            {
                 myArray += arr[i] + " ";
            }
            console.log(myArray);
        }

        function eleven(){
            var myArray = [1,2,3,4,5];
            console.log("Исходный массив: ");
            printArray(myArray);

            var newArray = reverseArray(myArray);
            console.log("Новый массив после reverseArray: ");
            printArray(newArray);

            reverseArrayInPlace(myArray);
            console.log("Исходный массив после reverseArrayInPlace: ");
            printArray(myArray);
        }
        //12
        function deepEqual(value1, value2) {
            if(typeof(value1) != 'object' && typeof(value2) != 'object') 
                return value1 === value2;
            if(value1 == null && value2 == null) 
                return true;
            if(value1 == null || value2 == null) 
                return false;

            let keys1 = Object.keys(value1);
            let keys2 = Object.keys(value2);
            
            if(keys1.length != keys2.length) 
                return false;

            for(key of keys1)
                if(!keys2.includes(key) || !deepEqual(value1[key], value2[key])) 
                    return false;
            
            return true;
        }

        function twelve(){
            console.log(deepEqual(1, 1)); // true
            console.log(deepEqual(1, 2)); // false
            console.log(deepEqual('yes', 'yes')); // true
            console.log(deepEqual('yes', 'no')); // false
            console.log(deepEqual({ a: 1, b: 2 }, { a: 1, b: 2 })); // true
            console.log(deepEqual({ a: 1, b: 2 }, { a: 1, b: 3 })); // false
            console.log(deepEqual(null, null)); // true
        }
        //13
        function thirteen(){
            const arrays = [
                [1, 2, 3], 
                [4, 5], 
                [6]
            ];

            const collapsedArray = arrays.reduce((accumulator, currentArray) => {
                return accumulator.concat(currentArray);
            }, []);

            console.log(collapsedArray);
        }
    </script>
    <p><button onclick="clearC()"><b>Очистить консоль</b></button></p>
    <button onclick="one()">Задание 1</button>
    <button onclick="two()">Задание 2</button>
    <button onclick="three()">Задание 3</button>    
    <button onclick="writeGrid()">Задание 4</button>
    <button onclick="FizzBuzz()">Задание 5</button>
    <button onclick="createChessBoard()">Задание 6</button>
    <button onclick="seven()">Задание 7</button>
    <button onclick="eight()">Задание 8</button>
    <button onclick="nine()">Задание 9</button>
    <button onclick="ten()">Задание 10</button>
    <button onclick="eleven()">Задание 11</button>
    <button onclick="twelve()">Задание 12</button>
    <button onclick="thirteen()">Задание 13</button>
</body>
</html>
```
## <p align="center">_Вывод_</p>
В ходе выполнения данной лабораторной работы я ознакомился с функциями в JavaScript. Я изучил, как объявлять функции, передавать аргументы и возвращать значения, а также проделал много работы с циклом for.
