| Таблица / №                          | Логическое имя атрибута  | Физическое имя          | Тип данных | Параметры | Ограничения              |
|--------------------------------------|--------------------------|-------------------------|------------|-----------|--------------------------|
| client_level (Уровень клиента)       |                          |                         |            |           |                          |
| 1                                    | Идентификатор уровня     | id_level                | INT        |           | PK, Auto Increment       |
| 2                                    | Название уровня          | name                    | VARCHAR    | 50        | Mandatory                |
| 3                                    | Процент скидки           | discount_percent        | DECIMAL    | 5,2       | Mandatory, CHECK (0–100) |
| client (Клиент)                      |                          |                         |            |           |                          |
| 1                                    | Идентификатор клиента    | id_client               | INT        |           | PK, Auto Increment       |
| 2                                    | Фамилия                  | last_name               | VARCHAR    | 50        | Mandatory                |
| 3                                    | Имя                      | first_name              | VARCHAR    | 50        | Mandatory                |
| 4                                    | Отчество                 | middle_name             | VARCHAR    | 50        |                          |
| 5                                    | Телефон                  | phone                   | VARCHAR    | 20        | Mandatory, Unique        |
| 6                                    | Email                    | email                   | VARCHAR    | 100       | Unique                   |
| 7                                    | Дата рождения            | birth_date              | DATE       |           |                          |
| 8                                    | Пол                      | gender                  | CHAR       | 1         | CHECK (M, F)             |
| 9                                    | Дата регистрации         | registration_date       | DATE       |           | Mandatory                |
| 10                                   | Уровень клиента          | level_id                | INT        |           | Foreign Key              |
| job_position (Должность)             |                          |                         |            |           |                          |
| 1                                    | Идентификатор должности  | id_position             | INT        |           | PK, Auto Increment       |
| 2                                    | Название должности       | name                    | VARCHAR    | 50        | Mandatory                |
| 3                                    | Описание                 | description             | VARCHAR    | 255       |                          |
| branch (Филиал)                      |                          |                         |            |           |                          |
| 1                                    | Идентификатор филиала    | id_branch               | INT        |           | PK, Auto Increment       |
| 2                                    | Название                 | name                    | VARCHAR    | 100       | Mandatory                |
| 3                                    | Адрес                    | address                 | VARCHAR    | 255       | Mandatory                |
| 4                                    | Телефон                  | phone                   | VARCHAR    | 20        | Mandatory                |
| employee (Сотрудник)                 |                          |                         |            |           |                          |
| 1                                    | Идентификатор сотрудника | id_employee             | INT        |           | PK, Auto Increment       |
| 2                                    | Фамилия                  | last_name               | VARCHAR    | 50        | Mandatory                |
| 3                                    | Имя                      | first_name              | VARCHAR    | 50        | Mandatory                |
| 4                                    | Отчество                 | middle_name             | VARCHAR    | 50        |                          |
| 5                                    | Телефон                  | phone                   | VARCHAR    | 20        | Mandatory, Unique        |
| 6                                    | Email                    | email                   | VARCHAR    | 100       | Unique                   |
| 7                                    | Дата найма               | hire_date               | DATE       |           | Mandatory                |
| 8                                    | Должность                | position_id             | INT        |           | Foreign Key              |
| 9                                    | Филиал                   | branch_id               | INT        |           | Foreign Key              |
| service_category (Категория услуг)   |                          |                         |            |           |                          |
| 1                                    | Идентификатор категории  | id_category             | INT        |           | PK, Auto Increment       |
| 2                                    | Название                 | name                    | VARCHAR    | 50        | Mandatory, Unique        |
| 3                                    | Описание                 | description             | VARCHAR    | 255       |                          |
| 4                                    | Порядок сортировки       | sort_order              | INT        |           |                          |
| service (Услуга)                     |                          |                         |            |           |                          |
| 1                                    | Идентификатор услуги     | id_service              | INT        |           | PK, Auto Increment       |
| 2                                    | Название                 | name                    | VARCHAR    | 100       | Mandatory                |
| 3                                    | Описание                 | description             | VARCHAR    | 255       |                          |
| 4                                    | Длительность (мин)       | duration_min            | INT        |           | Mandatory, CHECK (>0)    |
| 5                                    | Стоимость                | price                   | DECIMAL    | 10,2      | Mandatory, CHECK (>=0)   |
| 6                                    | Категория                | category_id             | INT        |           | Foreign Key              |
| employee_service (Услуги сотрудника) |                          |                         |            |           |                          |
| 1                                    | Сотрудник                | employee_id             | INT        |           | PK, Foreign Key          |
| 2                                    | Услуга                   | service_id              | INT        |           | PK, Foreign Key          |
| employee_schedule (График работы)    |                          |                         |            |           |                          |
| 1                                    | Идентификатор записи     | id_schedule             | INT        |           | PK, Auto Increment       |
| 2                                    | Дата                     | date                    | DATE       |           | Mandatory                |
| 3                                    | Время начала             | start_time              | TIME       |           | Mandatory                |
| 4                                    | Время окончания          | end_time                | TIME       |           | Mandatory, CHECK         |
| 5                                    | Рабочий день             | is_working              | BOOLEAN    |           | Default TRUE             |
| 6                                    | Сотрудник                | employee_id             | INT        |           | Foreign Key              |
| appointment_status (Статус записи)   |                          |                         |            |           |                          |
| 1                                    | Идентификатор статуса    | id_status               | INT        |           | PK, Auto Increment       |
| 2                                    | Название                 | name                    | VARCHAR    | 20        | Mandatory, Unique        |
| appointment (Запись на прием)        |                          |                         |            |           |                          |
| 1                                    | Идентификатор записи     | id_appointment          | INT        |           | PK, Auto Increment       |
| 2                                    | Дата и время             | appointment_datetime    | DATETIME   |           | Mandatory                |
| 3                                    | Комментарий              | comment                 | VARCHAR    | 255       |                          |
| 4                                    | Итоговая стоимость       | total_price             | DECIMAL    | 10,2      |                          |
| 5                                    | Клиент                   | client_id               | INT        |           | Foreign Key              |
| 6                                    | Сотрудник                | employee_id             | INT        |           | Foreign Key              |
| 7                                    | Филиал                   | branch_id               | INT        |           | Foreign Key              |
| 8                                    | Статус                   | status_id               | INT        |           | Foreign Key              |
| appointment_service (Состав записи)  |                          |                         |            |           |                          |
| 1                                    | Идентификатор позиции    | id_appointment_service  | INT        |           | PK, Auto Increment       |
| 2                                    | Количество               | quantity                | INT        |           | Default 1, CHECK (>0)    |
| 3                                    | Цена на момент           | price_at_moment         | DECIMAL    | 10,2      | Mandatory                |
| 4                                    | Запись                   | appointment_id          | INT        |           | Foreign Key              |
| 5                                    | Услуга                   | service_id              | INT        |           | Foreign Key              |
| payment (Платеж)                     |                          |                         |            |           |                          |
| 1                                    | Идентификатор платежа    | id_payment              | INT        |           | PK, Auto Increment       |
| 2                                    | Дата и время оплаты      | payment_datetime        | DATETIME   |           | Mandatory                |
| 3                                    | Сумма                    | amount                  | DECIMAL    | 10,2      | Mandatory                |
| 4                                    | Способ оплаты            | payment_method          | VARCHAR    | 30        | Mandatory                |
| 5                                    | Статус                   | status                  | VARCHAR    | 20        | Mandatory                |
| 6                                    | Внешний ID               | external_transaction_id | VARCHAR    | 100       |                          |
| 7                                    | Запись                   | appointment_id          | INT        |           | Foreign Key              |
