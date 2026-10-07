# Сутності та атрибути

### User:

- `User_id`: UUIDv7 (PK)
- `Email`: string (UK)
- `Password_hash`: string
- `First_name`: string
- `Last_name`: string
- `Registration_date`: timestamp

### Researcher:

- `Researcher_id`: UUIDv7 (PK)
- `User_id`: UUIDv7 (FK)
- `OrcidD`: string (UK)
- `ScopusID`: string (UK)
- `Google_scholar`: string (UK)

### Research:

- `Research_id`: UUIDv7 (PK)
- `Research_name`: string
- `Authors`: UUIDv7[] (FK)
- `Categories_id`: UUIDv7[] (FK)

### Category:

- `Category_id`: UUIDv7 (PK)
- `Category_name`: string (UK)

### Form:

- `Form_id`: UUIDv7 (PK)
- `Research_id`: UUIDv7 (FK)
- `Questions`: JSON

### Answer:

- `Answer_id`: UUIDv7 (PK)
- `Form_id`: UUIDv7 (FK)
- `User_id`: UUIDv7 (FK)
- `Answer`: JSON

# Зв'язки

1. #### `User` -відповідає- `Researcher` (1/1):
   - Один користувач може бути пов'язаним з один дослідником (1:1)
2. #### `Researcher` -створює- `Research` (1..N/0..N):
   - У дослідника є будь яка кількість досліджень (1:0..N)
   - У дослідження має бути як мінімум один дослідник (1:1..N)
3. #### `Research` -належить- `Category` (1..N/1..N):
   - У Дослідження має бути як мінімм одна категорія (1:1..N)
   - У категорії має бути як мінімум одна категорія (1:1..N)
4. #### `Research` -складається-з- `Form` (1/1..N):
   - У дослідження має бути як мінімм одна форма (1:1..N)
   - Форма відовідає лише одному дослідженню (1:1..N)
5. ### `Form` -має- `Answer` (1/0..N):
   - У форми може бути, або не бути відповідей (1:0..N)
   - У відповіді існує лише на одну форму (1:1)
6. ### `User` -надає- `Answer` (1/0..N):
   - У користувача може надавати будь яку кількість відповідей (1:0..N)
   - У відповіді має бути лише один автор (1:1)

# Критерії прийняття

1. #### Артефакти:
   - ER модель в Mermaid/PlantUML
   - Рендер (візуалізація) er моделі. Повинна бути гарною, та візуально не засміченою
2. #### Важливі перевірки:
   - Правильна кардинальність яка має сенс
   - Без прив'язки до БД
   - Ніяких асоціативних сутностей, якщо вони не несуть з собою додаткового змісту
