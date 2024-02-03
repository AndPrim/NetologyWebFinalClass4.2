# NetologyWebFinalClass4.2 (План внедрения автоматизации тестирования на проект).

## 1. Предлогаю перечень сценариев для автоматизации тестирования:
### Доступ к формам записи:
1. Доступ на страницу профессии "Тестировщик ПО" с формой записи на курс  с главной страницы Нетологии: Блок "Программирование" - "Тестировщик ПО" 
- Рузультат: открыта главная страницу профессии "Тестировщик ПО" с формой записи на консультацию: "Поможем подобрать обучение".
2. Доступ на страницу профессии "Тестировщик ПО" с формой записи на курс  с главной страницы Нетологии  через кнопку "Каталог курсов": "Каталог курсов"- "Программирование" - "Тестировщик ПО"
- Рузультат: открыта главная страницу профессии "Тестировщик ПО" с формой записи на консультацию: "Поможем подобрать обучение".
3. Доступ на страницу формы записи на курс "Тестировщик ПО"  с главной страницы Нетологии:Блок "Программирование" -  "Тестировщик ПО" - прокрутка до конца страницы
- Результат: открыта страница с формой для записи на курс "Тестировщик ПО".
4. Доступ на страницу формы записи на курс "Тестировщик ПО"  с главной страницы Нетологии через кнопку "Записаться": "Каталог курсов"- "Программирование" - "Тестировщик ПО" - кнопка "Записаться"
- Результат: открыта страница с формой для записи на курс "Тестировщик ПО".
### Тестирование форм записи:
**Валидные значения**
1. Блок "Запишитесь на курс" кнопка "Записаться" (Валидные значения): 
- Имя: 2-60 символов: кириллица, символ "-", "ё"
- телефон: 10 символов: цифры, первая цифра "7"
- Действие: нажать на кнопку "Записаться"
- Результат: открыта страница оплаты, в базу данных сохраняется информация о пользователе и направляется извещение менеджеру.
2. Блок "Запишитесь на курс" кнопка "Получить консультацию" (Валидные значения): 
- Имя: 2-60 символов: кириллица, символ "-", "ё"
- телефон: 10 символов: цифры, первая цифра "7"
- Действие: нажать на кнопку "Получить консультацию"
- Итог: Выводится сообщение, что данные пользователя получены и ему необходимо в указанный срок ожидать звонка. Информация вносится в БД и направляется извещение менеджеру.
**Незаполненные поля блока "Запишитесь на курс"**
1. Отправка пустых полей кнопкой "Записаться"
- Поля Имя/Телефон не заполнены
- нажать на кнопку "Записаться"
- результат: Поля Имя/Телефон окрашены в красный цвет, у каждого поля возникает уведомление "Обязательно для заполнения", данные в БД не направляются
2. Отправка пустых полей кнопкой "Получить консультацию""
- Поля Имя/Телефон не заполнены
- нажать на кнопку "Записаться"
- результат: Поля Имя/Телефон окрашены в красный цвет, у каждого поля возникает уведомление "Обязательно для заполнения", данные в БД и информация менеджеру не направляются
**Проверка на валидное заполнение полей блока "Запишитесь на курс"**
1. Проверка валидации поля "Имя", пограничные значения
- телефон: 10 символов (валидное значение).
- Имя: 1 валидный символ (Валидное значение: этническое имя)
- нажать на кнопку "Записаться"/"Получить консультацию"
- _Фактический результат_: Уведомление красного цвета "Не должно быть короче 2-х символов", данные в БД и информация менеджеру не направляются
- _Ожидаемый результат_:  Пользователь получает уведомление, что данные пользователя получены и ему необходимо в указанный срок ожидать звонка. Информация вносится в БД и направляется извещение менеджеру.
2. Проверка валидации поля "Имя", пограничные значения
- телефон: 10 символов: валидное значение
- Имя: 3 валидных символа
- нажать на кнопку "Записаться"/"Получить консультацию"
- Результат: Пользователь получает уведомление, что данные пользователя получены и ему необходимо в указанный срок ожидать звонка. Информация вносится в БД и направляется извещение менеджеру
3. Проверка валидации поля "Имя", пограничные значения
- телефон: валидное значение
- Имя: 59 валидных символов
- нажать на кнопку "Записаться"/"Получить консультацию"
- Результат: Пользователь получает уведомление, что данные пользователя получены и ему необходимо в указанный срок ожидать звонка. Информация вносится в БД и направляется извещение менеджеру
4. Проверка валидации поля "Имя", пограничные значения
- телефон: валидное значение
- Имя: 60 валидных символов
- нажать на кнопку "Записаться"/"Получить консультацию"
- Результат: Пользователь получает уведомление, что данные пользователя получены и ему необходимо в указанный срок ожидать звонка. Информация вносится в БД и направляется извещение менеджеру
5. Проверка валидации поля "Имя", пограничные значения
- телефон - 10 символов: цифры
- Имя: Попытка ввести 61-й валидный символ
- Результат: 61-й символ в поле ввести невозможно.
6. Проверка валидации поля "Имя", невалидные значения
- телефон - 10 символов: цифры
- Имя: Попытка ввести символ латиницы/этнические символы/цифру/спец символ кроме "-"
- Результат: символы в поле ввести невозможно
7. Проверка валидации поля "Телефон", пограничные значения
- Имя: Валидное значение
- телефон: 9 цифр, первая 7
- нажать на кнопку "Записаться"/"Получить консультацию"
- Результат: Уведомление "Неверный формат", данные в БД и информация менеджеру не направляются
8. Проверка валидации поля "Телефон", пограничные значения
- Имя: Валидное значение
- телефон: попытка ввести 11 цифр 
- Результат: 11-й символ в поле ввести невозможно
9. Проверка валидации поля "Телефон", невалидные значения
- Имя: Валидное значение
- телефон: попытка ввести любые символы за исключением арабских цифр
- Результат: символы в поле ввести невозможно
10. Проверка валидации поля "Телефон", невалидные значения
- Имя: Валидное значение
- телефон: ввод первого символа не соответствующего "7"
- Результат: Уведомление "Неверный формат", данные в БД не обновляются

## 2. Подбор инструментов с обоснованием выбора.
- Среда разработчика: *IDEA*. Имеется практический опыт работы. Дружественный интерфейс. Большое количество информации в интернете по вопросам применения.
- Для работы с базами данных *Docker*. Имеется определенный опыт. Достаточно просто подключить.
- Через Docker буду работать с *MySQL*. Имеется определенный опыт. Много информации в инете по большому количеству вариантов применения.
- Проект на *Gradle*, с полным покетом библиотек определюсь во время тестирования.
- Библиотека *JUNIT5* так как мне он нравится.
- *Selenide* для автоматизации работы с веб формами.
- *Lombok* для сокращения и читаемости кода.
- *Faker* для генерации случайных имени и чисел для заполнения форм
- *Сommons-dbutils* и *mysql* для работы с базами данных
- *Allure* для составления отчетности.

## 3. Перечень необходимых разрешений, данных и доступов.
Доступ к БД, к ресурсу отправляющему сообщение менеджеру.

## 4. Перечень и описание возможных рисков при автоматизации.
- Изменение структуры вебприложения.
- Желательно иметь макет базы данных, чтоб не испортить основную.
- Сложное вебпреложение без id-test меток.

## 5. Перечень необходимых специалистов для автоматизации.
- Мануальный тестировщик
- Инженер по автоматизированному тестированию

## 6. Интервальная оценка с учётом рисков в часах.
- 6 часа - ручное тестирование + оформление найденных багов
- 20 часа - написание структуры проекта
- 16 часа - написание тестов
- 1.5 часа - формирование отчетности
