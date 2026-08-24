# DB11

1. branches (Филиалы компании)
Хранит адреса филиалов компании.

id — SERIAL (PRIMARY KEY)

address — VARCHAR(255) NOT NULL UNIQUE

2. department_types (Типы подразделений)
Справочник типов структуры («Отдел», «Группа», «Департамент»).

id — SERIAL (PRIMARY KEY)

name — VARCHAR(50) NOT NULL UNIQUE

3. departments (Структурные подразделения)
Хранит конкретные отделы и подразделения компании.

id — SERIAL (PRIMARY KEY)

name — VARCHAR(255) NOT NULL UNIQUE

department_type_id — INT NOT NULL (FOREIGN KEY -> department_types.id)

4. positions (Должности)
Справочник должностей («ведущий разработчик», «специалист по персоналу» и т.д.).

id — SERIAL (PRIMARY KEY)

name — VARCHAR(150) NOT NULL UNIQUE

5. projects (Проекты)
Справочник проектов («Севастополь ТВ», «Газпромбанк Бирюзова» и др.).

id — SERIAL (PRIMARY KEY)

name — VARCHAR(200) NOT NULL UNIQUE

6. employees (Сотрудники)
Основная таблица сотрудников компании.

id — SERIAL (PRIMARY KEY)

full_name — VARCHAR(150) NOT NULL

salary — NUMERIC(10, 2) NOT NULL

hire_date — DATE NOT NULL

position_id — INT NOT NULL (FOREIGN KEY -> positions.id)

department_id — INT NOT NULL (FOREIGN KEY -> departments.id)

branch_id — INT NOT NULL (FOREIGN KEY -> branches.id)

7. employee_projects (Назначения на проекты)
Таблица связи Many-to-Many между сотрудниками и проектами.

employee_id — INT NOT NULL (FOREIGN KEY -> employees.id)

project_id — INT NOT NULL (FOREIGN KEY -> projects.id)

PRIMARY KEY (employee_id, project_id)

<img width="1111" height="612" alt="image" src="https://github.com/user-attachments/assets/eb245176-f714-444c-8b5f-6914996bc806" />

