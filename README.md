# Django Project with PostgreSQL and python-dotenv

This is a Django project configured to use PostgreSQL as the database and `python-dotenv` to manage environment variables. This README will guide you through setting up the project locally.

## Prerequisites

Before you begin, ensure you have the following installed on your machine:

- Python 3.x
- PostgreSQL
- Git

## Setup Instructions

1. **Clone the repository**

   ```bash
   git clone https://github.com/MehediMK/django-with-postgresql.git
   cd django-with-postgresql
   ```

2. **Create and activate a virtual environment**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install the dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Set up the PostgreSQL database**

   - Create a new PostgreSQL database:

     ```sql
     CREATE DATABASE test_db;
     CREATE USER db_user WITH PASSWORD 'password';
     ALTER ROLE db_user SET client_encoding TO 'utf8';
     ALTER ROLE db_user SET default_transaction_isolation TO 'read committed';
     ALTER ROLE db_user SET timezone TO 'UTC';
     GRANT ALL PRIVILEGES ON DATABASE test_db TO db_user;
     ```

5. **Configure environment variables**

   - Create a `.env` file in the project root with the following content:

     ```env
     DEBUG=True
     NAME=test_db
     USER=db_user
     PASSWORD=password
     HOST=localhost
     PORT=5432
     ```

6. **Apply migrations**

   ```bash
   python manage.py migrate
   ```

7. **Run the development server**

   ```bash
   python manage.py runserver
   ```

   You should now be able to access the project at `http://127.0.0.1:8000/`.

## Additional Commands

- **Create a superuser**

  ```bash
  python manage.py createsuperuser
  ```

- **Run tests**

  ```bash
  python manage.py test
  ```

## Contributing

Feel free to open issues or submit pull requests if you find any bugs or have new features you want to add.