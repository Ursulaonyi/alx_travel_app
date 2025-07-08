# ALX Travel App

A Django-based travel listing platform that allows users to create, manage, and browse travel listings.

## Features

- RESTful API built with Django REST Framework
- MySQL database integration
- Swagger API documentation
- CORS support for frontend integration
- Celery integration for background tasks
- Environment-based configuration
- User authentication and authorization

## Tech Stack

- **Backend**: Django 4.2+
- **API**: Django REST Framework
- **Database**: MySQL
- **Documentation**: Swagger (drf-yasg)
- **Task Queue**: Celery with Redis
- **Environment Management**: django-environ

## Setup Instructions

### Prerequisites

- Python 3.8+
- MySQL 8.0+
- Redis (for Celery)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/alx_travel_app.git
cd alx_travel_app


2. Create a virtual environment and activate it:

bashpython -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

Install dependencies:

bashcd alx_travel_app
pip install -r requirements.txt

Set up environment variables:

bashcp .env.example .env
# Edit .env with your database credentials and other settings

Set up MySQL database:

sqlCREATE DATABASE alx_travel_db;
CREATE USER 'your_user'@'localhost' IDENTIFIED BY 'your_password';
GRANT ALL PRIVILEGES ON alx_travel_db.* TO 'your_user'@'localhost';
FLUSH PRIVILEGES;

Run migrations:

bashpython manage.py makemigrations
python manage.py migrate

Create a superuser:

bashpython manage.py createsuperuser

Start the development server:

bashpython manage.py runserver
API Documentation
Once the server is running, you can access the API documentation at:

Swagger UI: http://localhost:8000/swagger/
ReDoc: http://localhost:8000/redoc/
JSON Schema: http://localhost:8000/swagger.json

Running Celery (Optional)
To run background tasks:

Start Redis server
Start Celery worker:

bashcelery -A alx_travel_app worker --loglevel=info

Start Celery beat (for periodic tasks):

bashcelery -A alx_travel_app beat --loglevel=info
API Endpoints
Listings

GET /api/listings/ - List all listings
POST /api/listings/ - Create a new listing (requires authentication)
GET /api/listings/{id}/ - Retrieve a specific listing
PUT /api/listings/{id}/ - Update a listing (requires authentication)
DELETE /api/listings/{id}/ - Delete a listing (requires authentication)
GET /api/listings/my_listings/ - Get current user's listings
GET /api/listings/featured/ - Get featured listings

Query Parameters

location - Filter by location (partial match)
price_min - Filter by minimum price
price_max - Filter by maximum price

Development
Running Tests
bashpython manage.py test
Code Style
This project follows PEP 8 style guidelines. You can check your code style using:
bashflake8 .
Contributing

Fork the repository
Create a feature branch
Make your changes
Add tests for new functionality
Ensure all tests pass
Submit a pull request

License
This project is licensed under the MIT License.
Support
For support, please open an issue in the GitHub repository.
