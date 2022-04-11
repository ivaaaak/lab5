# lab5
Реализовать консольное приложение, которое реализует управление коллекцией объектов в интерактивном режиме. В коллекции необходимо хранить объекты класса Person, описание которого приведено ниже.

Разработанная программа должна удовлетворять следующим требованиям:

Класс, коллекцией экземпляров которого управляет программа, должен реализовывать сортировку по умолчанию.
Все требования к полям класса (указанные в виде комментариев) должны быть выполнены.
Для хранения необходимо использовать коллекцию типа java.util.Hashtable
При запуске приложения коллекция должна автоматически заполняться значениями из файла.
Имя файла должно передаваться программе с помощью: переменная окружения.
Данные должны храниться в файле в формате json
Чтение данных из файла необходимо реализовать с помощью класса java.io.FileReader
Запись данных в файл необходимо реализовать с помощью класса java.io.OutputStreamWriter
Все классы в программе должны быть задокументированы в формате javadoc.
Программа должна корректно работать с неправильными данными (ошибки пользовательского ввода, отсутсвие прав доступа к файлу и т.п.).
В интерактивном режиме программа должна поддерживать выполнение следующих команд:

help : вывести справку по доступным командам
info : вывести в стандартный поток вывода информацию о коллекции (тип, дата инициализации, количество элементов и т.д.)
show : вывести в стандартный поток вывода все элементы коллекции в строковом представлении
insert null {element} : добавить новый элемент с заданным ключом
update id {element} : обновить значение элемента коллекции, id которого равен заданному
remove_key null : удалить элемент из коллекции по его ключу
clear : очистить коллекцию
save : сохранить коллекцию в файл
execute_script file_name : считать и исполнить скрипт из указанного файла. В скрипте содержатся команды в таком же виде, в котором их вводит пользователь в интерактивном режиме.
exit : завершить программу (без сохранения в файл)
remove_lower {element} : удалить из коллекции все элементы, меньшие, чем заданный
replace_if_greater null {element} : заменить значение по ключу, если новое значение больше старого
replace_if_lowe null {element} : заменить значение по ключу, если новое значение меньше старого
max_by_hair_color : вывести любой объект из коллекции, значение поля hairColor которого является максимальным
filter_by_location location : вывести элементы, значение поля location которых равно заданному
filter_starts_with_name name : вывести элементы, значение поля name которых начинается с заданной подстроки
Формат ввода команд:

Все аргументы команды, являющиеся стандартными типами данных (примитивные типы, классы-оболочки, String, классы для хранения дат), должны вводиться в той же строке, что и имя команды.
Все составные типы данных (объекты классов, хранящиеся в коллекции) должны вводиться по одному полю в строку.
При вводе составных типов данных пользователю должно показываться приглашение к вводу, содержащее имя поля (например, "Введите дату рождения:")
Если поле является enum'ом, то вводится имя одной из его констант (при этом список констант должен быть предварительно выведен).
При некорректном пользовательском вводе (введена строка, не являющаяся именем константы в enum'е; введена строка вместо числа; введённое число не входит в указанные границы и т.п.) должно быть показано сообщение об ошибке и предложено повторить ввод поля.
Для ввода значений null использовать пустую строку.
Поля с комментарием "Значение этого поля должно генерироваться автоматически" не должны вводиться пользователем вручную при добавлении.
Описание хранимых в коллекции классов:

public class Person {
    private Integer id; //Поле не может быть null, Значение поля должно быть больше 0, Значение этого поля должно быть уникальным, Значение этого поля должно генерироваться автоматически
    private String name; //Поле не может быть null, Строка не может быть пустой
    private Coordinates coordinates; //Поле не может быть null
    private java.time.LocalDateTime creationDate; //Поле не может быть null, Значение этого поля должно генерироваться автоматически
    private float height; //Значение поля должно быть больше 0
    private float weight; //Значение поля должно быть больше 0
    private Color hairColor; //Поле не может быть null
    private Country nationality; //Поле может быть null
    private Location location; //Поле может быть null
}
public class Coordinates {
    private Integer x; //Максимальное значение поля: 172, Поле не может быть null
    private Double y; //Поле не может быть null
}
public class Location {
    private Long x; //Поле не может быть null
    private Integer y; //Поле не может быть null
    private int z;
}
public enum Color {
    RED,
    BLUE,
    ORANGE;
}
public enum Country {
    USA,
    CHINA,
    VATICAN,
    NORTH_KOREA;
}
Отчёт по работе должен содержать:

Текст задания.
Диаграмма классов разработанной программы.
Исходный код программы.
Выводы по работе.
Вопросы к защите лабораторной работы:

Коллекции. Сортировка элементов коллекции. Интерфейсы java.util.Comparable и java.util.Comparator.
Категории коллекций - списки, множества. Интерфейс java.util.Map и его реализации.
Параметризованные типы. Создание параметризуемых классов. Wildcard-параметры.
Классы-оболочки. Назначение, область применения, преимущества и недостатки. Автоупаковка и автораспаковка.
Потоки ввода-вывода в Java. Байтовые и символьные потоки. "Цепочки" потоков (Stream Chains).
Работа с файлами в Java. Класс java.io.File.
Пакет java.nio - назначение, основные классы и интерфейсы.
Утилита javadoc. Особенности автоматического документирования кода в Java.
