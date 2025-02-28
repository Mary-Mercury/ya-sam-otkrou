# ya-sam-otkrou
бмк на 30.10.2024

Добрый день, многоуважаемые. Раз вы отсканировали QR, значит вы хотите выполнить задание. Да будет так. Оно не сложное.
В этой пояснительной записке Я расскажу вам как решить данное задание. Здесь будет теоритический материал, основываясь на котором вы будете решать задачу.
Начнем с т.н "бизнес-логики".
У вас стоит задача написать программу "Укадай число", суть которой угадать случайно загаданное компьютером число за ограниченное количество попыток. Компьютер загадывает случайное число в определённом диапазоне, и вы, вводя свои догадки, получает подсказки, больше или меньше его число, чем загаданное.

У программы есть 5 основных функций, это:
1. Генерация случайного числа в указанном диапазоне.
2. Счётчик попыток: ограничение на количество попыток, после которого игра заканчивается.
3. Основной цикл. Ввод числа пользователем.
4. Основной цикл. Сравнение введённого числа с загаданным числом:
     - Если угадал, программа завершает игру и поздравляет пользователя.
     - Если не угадал, программа подсказывает, больше или меньше загаданное число.
5. Конец игры: если попытки закончились, программа сообщает загаданное число и завершает игру.

Наша цель - написать алгоритм, в котором компьютер загадывает случайное число, а пользователь должен угадать его за ограниченное количество попыток. Игра должна давать подсказки - больше или меньше загаданное число, и завершаться, если попытки закончились или число угадано.

Для достижения первой функции нам потребуется импортировать встроенный модуль для генераций целых чисел. В Python за это ответсвенен модуль random. Модуль имеет большое кол-во функций, но вкрадце опишу лишь несколько из них:
- random(): генерирует случайное число от 0.0 до 1.0
- randint(): возвращает случайное число из определенного диапазона
- randrange(): возвращает случайное число из определенного набора чисел

Какую именно функцию использовать, решать уже вам.

Для достижения второй функции, достаточно просто инициализировать переменную с целочисленным значнием. Это и будет нашим кол-вом попыток. Пример типа того: attempts_left = 10

Основной цикл. Все что помечено основным циклом, будет реализовано непосредсвенно в нем. Основной цикл - это цикл повторения. Т.к задание подразумевает реализацию попыток, то следует использовать цикл while, чтобы повторять попытки, пока у игрока они есть. Каждая итерация будет запрашивать у пользователя ввод числа, проверять его и выдавать подсказки.

Ввод числа пользователем. В Python имеется лишь один метод для чтения данных из консоли, это метод input(). Данный метод присваивается переменной и в круглые скобки передается промт который в дальнейшем будет отображаться в консоли (это не обязательный параметр). Есть одна загвоздка в этом методе, он возвращает в переменную лишь строчные значения. Что я имею ввиду: в ЯП есть множество типов данных и каждые со своими свойствами. Со строчными типами данных (т.е текст) нельзя проводить математические операции, в отличии конечно же от целочисленных или дробных значений. Поэтому, чтобы получить именно целочисленное значение, а не строчное, потребуется произвести преобразование в соответсвующий тип данных. Для этого метод input() нужно дополнительно завернуть в метод int().

Сравнение введённого числа с загаданным числом. Сравниваем введённое число с загаданным и выводим подсказки с помощью конструкции if-elif-else:
- Если предполагаемое значение пользователем == загаданное число компьютером, выводим сообщение о победе, игрок угадал число, и цикл завершится (break).
- Если предполагаемое значение пользователем < загаданное число компьютером, выводим подсказку, что загаданное число больше.
- Если предполагаемое значение > загаданное число компьютером, выводим подсказку, что загаданное число меньше.

Каждый раз, когда пользователь не угадывает число, количество попыток уменьшается на 1. Для этого просто используем операцию вычитания для переменной, в которую мы указали кол-во попыток. После этого можем выводить, сколько попыток осталось, чтобы игрок видел свой прогресс.

![image](https://github.com/user-attachments/assets/a6563c1f-6cc5-4d2e-963e-19ae621da470)

Прикрепил пикчу с кода чтобы вы понимали о чем идет речь.

 Конец игры. После завершения цикла while, проверяем, остались ли у игрока попытки. Если переменная в которой мы указали кол-во попыток равна 0, это значит, что все попытки были использованы, и игра завершена проигрышем. Мы сообщаем игроку загаданное число, чтобы он узнал результат игры.


Удачи чуваки

![image](https://github.com/user-attachments/assets/ad05db60-2fac-406f-b9db-6c350e6fd8ec)

