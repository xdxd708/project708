документация "project708".
========================

#1. Описание проекта:
========================
Проект 708 представляет собой простое приложение интернет-магазина, разработанное на языке программирования C# с использованием Windows Forms. Приложение позволяет пользователям просматривать продукты, добавлять их в корзину, а также осуществлять регистрацию и вход в систему.

#2. Структура проекта:
========================

*Форма "main" (main.cs):
Основная форма приложения, содержащая список продуктов и функционал для работы с корзиной покупок.
*Форма "registration" (registration.cs):
*Форма для регистрации новых пользователей в системе.
*Форма "profile" (profile.cs):
*Форма, отображающая профиль пользователя и позволяющая загрузить фотографию профиля.
*Форма "korzuna" (korzuna.cs):
*Форма, отображающая содержимое корзины покупок.

#3. Описание классов и методов:
========================

*Класс "Product":
Описывает продукт с его названием и ценой.
>
public class Product
{
    public string Name { get; set; }
    public decimal Price { get; set; }

    public Product(string name, decimal price)
    {
        Name = name;
        Price = price;
    }
}
>
    *Класс "Cart":
Определяет корзину покупок, содержащую список добавленных продуктов.
>
public class Cart
{
    private static List<Product> items = new List<Product>();
    public static void AddItem(Product product)
    {
        items.Add(product);
    }
    public static List<Product> GetItems()
    {
        return items;
    }
}
>
    *Класс "database":
Обеспечивает подключение к базе данных MySQL и выполнение запросов.
>
internal class database
{
    MySqlConnection connection = new MySqlConnection("server=localhost;port=3306;username=root;password=root;database=project708");

    public void openconnection()
    {
        if (connection.State == System.Data.ConnectionState.Closed)
            connection.Open();
    }

    public void closeconnection()
    {
        if (connection.State == System.Data.ConnectionState.Open)
            connection.Close();
    }

    public MySqlConnection getConnection() 
    {
        return connection;
    }

}
>

    #4. Основной функционал:
========================

Добавление продуктов в корзину.
Отображение содержимого корзины.
Регистрация новых пользователей.
Вход в систему с проверкой учётных данных.

#5. Используемые технологии и библиотеки:
========================

C# (.NET Framework) для разработки логики приложения.
Windows Forms для создания пользовательского интерфейса.
MySQL для хранения данных о пользователях и продуктах.

#6. Примечания:
========================

Проект реализован в рамках учебной или демонстрационной цели и может быть доработан или расширен для более широкого использования.
Для корректной работы проекта необходимо наличие сервера MySQL и базы данных "project708", а также соответствующих таблиц.
Для успешного подключения к базе данных требуется наличие драйвера MySQL.Data.MySqlClient.

#7. Рекомендации по дальнейшему развитию:
========================

Добавление функционала оформления заказа.
Реализация системы управления товарами (добавление, удаление, изменение).
Улучшение интерфейса и добавление анимации для более привлекательного пользовательского опыта.
Реализация возможности изменения профиля пользователя (смена пароля, загрузка дополнительной информации).
Обработка исключений и улучшение безопасности при работе с базой данных.

#8. Авторство:

Проект создал Занин Илья в рамках итогового проекта по "основам алгоритмизации".
