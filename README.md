# student_control_panel
Панель управления студентами:  таблица со студентами с фильтрами и сортировкой, формой добавления нового студента. Реализовано с использвоанием API сервера.
Имеется возможность сохранения списка студентов и удаления студентов из списка на сервере (папка «backend» для запуска сервера с файлом README и с документацией по работе с сервером).
При запуске сервера в приложении выполняется проверка на наличие данных на сервере. Если данные есть, то выводится список студентов на экран. 

1. Для добавления студентов на странице имеется форма с полями, соответствующими данным студента:
  - имя,
  - фамилия,
  - отчество,
  - дата рождения,
  - год начала обучения,
  - факультет.

Форма имеет валидацию по следующим правилам:
- все поля обязательны для заполнения;
- текстовые поля ввода - возможен ввод только кирилицы;
- поля ввода для  цифровых значений - возможен ввод только цифры;
- дата рождения находится в диапазоне от 01.01.1900 до текущей даты;
- год начала обучения находится в диапазоне от 2000-го до текущего года.
Валидация происходит после нажатия на кнопку «Добавить», расположенную под полями для ввода. Если валидация прошла успешно, то все поля очищаются, а новый студент добавляется в таблицу/добавляется на сервер. В противном случае над кнопкой выводится сообщения с описанием ошибок для пользователя. 

2. Данные выводяться в табличном виде. Каждая строка таблицы содержит информацию об одном студенте. Колонки таблицы:
- Ф. И. О. студента.
- Факультет.
- Дата рождения и возраст в формате «28.04.2000 (20 лет)».
- Годы обучения и номер курса в формате «2021-2025 (3 курс)». Считается, что все студенты учатся четыре года. Если сентябрь года окончания обучения уже прошёл, в скобках вместо указания курса выводиться «закончил».
- 5-ая колонка - кнопка "Удалить студента". После нажатия на кнопку - студент удаляется из таблицы/удаляется с сервера.

3. Первая строка таблицы — заголовочная, в ней указаны заголовки колонок (Ф. И. О., факультет, дата рождения и возраст, годы обучения). При нажатии на ячейку заголовочной строки происходит сортировка (по возрастанию/убыванию) по соответствующим полям студентов:
- Ф. И. О. сортирует по соединённой строке из фамилии, имени и отчества по алфавиту.
- Факультет — по факультету по алфавиту.
- Дата рождения и возраст — по дате рождения.
- Годы обучения — по году начала обучения.

4. Также перед таблицей имеются фильтры (форма с полями для ввода), состоящие из полей:
- Ф. И. О. для поиска подстроки в фамилии, имени или отчестве.
- Факультет для поиска подстроки в названии факультета.
- Год начала обучения (точное совпадение).
- Год окончания обучения (точное совпадение).
При любых изменениях в полях для фильтрации содержимое таблицы изменяется в соответствии с указанными фильтрами. Если указано несколько фильтров, то все они применяются к массиву студентов по очереди.
