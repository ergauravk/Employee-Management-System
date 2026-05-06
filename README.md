# Employee Management System

A small Django application for managing employees, departments, and roles. It includes pages to view all employees, add records, remove records, and filter employees.

## Features

- Home dashboard with a shared Bootstrap layout
- Add employee form
- View all employees in a responsive table
- Remove employees from a dropdown list
- Filter employees by name, department, or role

## Requirements

- Python 3.12 or later recommended
- Django 6.x

## Setup

1. Create and activate a virtual environment.
2. Install dependencies:

```bash
pip install django
```

3. Apply database migrations:

```bash
python manage.py migrate
```

4. Run the development server:

```bash
python manage.py runserver
```

## Project Structure

- `employee/` - Django project settings and URL configuration
- `employee_app/` - Main app with models, views, and app URLs
- `templates/` - Shared HTML templates
- `db.sqlite3` - Local SQLite database

## Main Pages

- `/` - Home page
- `/all_emp/` - List all employees
- `/add_emp/` - Add a new employee
- `/remove_emp/` - Remove an employee
- `/filter_emp/` - Filter employees

## Notes

- Template files use a shared `base.html` layout with Bootstrap styling.
- If Bootstrap dropdowns do not open, make sure the Bootstrap JS bundle is loaded in `base.html`.
- Django may warn that `Employee.phone` uses `IntegerField(max_length=...)`; `max_length` is ignored for integer fields.

## Troubleshooting

- If a form POST fails with an `APPEND_SLASH` error, make sure the form action uses Django's `{% url %}` tag and points to the slash-ended route.
- If a template cannot be found, confirm `TEMPLATES['DIRS']` includes the project-level `templates/` folder in `employee/settings.py`.
- If the remove dropdown does not open, verify that the Bootstrap JavaScript bundle is included in `base.html`.
- If you see a warning about `Employee.phone`, consider changing the field to `CharField` for phone numbers or removing `max_length` from `IntegerField`.
