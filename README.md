# Complete Banking System

Full-stack banking app built with Django REST Framework and React. Includes secure auth, account management, social blogs with comments, transactions, and loans with admin approval.

## Features

- **Authentication and Security**

  - Email-based login, registration, JWT sessions
  - Password reset via OTP email
  - Optional Google sign-in (allauth)
  - Profile update with image avatar

- **Banking**

  - Balance view and history
  - Deposits and transfers between users (atomic, race-safe)
  - Transactions feed for incoming/outgoing and deposits

- **Loans**

  - Users can apply for loans with `amount`, `term_months`, and `interest_rate`
  - Admin can approve/reject; approval credits user balance and records a `LOAN` transaction

- **Social**

  - Blogs with optional image upload (served from `/media`)
  - Nested comments (1-level replies)
  - Admin can delete any blog

- **Users Directory**
  - List of users (name + account number)
  - Copy account number and search

## Tech Stack

- Backend: (core lang - python)Django, Django REST Framework, SimpleJWT, dj-rest-auth, allauth, Channels, MySQL
- Frontend:(core lang - javascript) React, Vite, MUI, Axios, React Router

## Prerequisites

- Python 3.10+
- Node.js 18+
- MySQL 8+

If you are a beginner, install in this order:

- Install Python (add to PATH)
- Install Node.js (LTS)
- Install MySQL Server and create a database (e.g., bankx)

## Backend Setup (Django)

1. Create and activate venv

```bash
cd backend
python -m venv venv
./venv/Scripts/activate
```

2. Install dependencies (if requirements.txt is missing on your machine, install these manually)

```bash

pip install django djangorestframework djangorestframework-simplejwt django-oauth-toolkit django-allauth dj-rest-auth[with_social] mysqlclient python-decouple Pillow django-cors-headers channels channels-redis

```

3. Configure database

- Create a MySQL database (e.g., `bankx`)

4. Migrate and create superuser

```bash
python manage.py migrate
python manage.py createsuperuser  # admin login for /admin and approvals
```

5. Run server

```bash
python manage.py runserver
```

## Frontend Setup (React + Vite)

1. Install deps

```bash
cd frontend/front
npm install
```

2. Run dev server

```bash
npm run dev

```
