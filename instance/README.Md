Superheroes API
This is a Flask-based RESTful API for managing superheroes and their powers. The API allows users to create, retrieve, update, and associate heroes with powers.

Technologies Used
Python
Flask
Flask-SQLAlchemy
Flask-Migrate
SQLite
Thunder client (for API testing)
Setup Instructions
Prerequisites
Ensure you have the following installed:

Python 3
pipenv (for virtual environment management)
Installation
Clone the repository:

git clone https://github.com/yourusername/superheroes-api.git
cd superheroes-api
Create and activate a virtual environment:

pipenv install
pipenv shell
Install dependencies:

pipenv install flask flask-sqlalchemy flask-migrate flask-cors
Initialize the database:

flask db init
flask db migrate -m "Initial migration"
flask db upgrade
Seed the database:

python seed.py
Start the Flask server:

python app.py
API Endpoints
Heroes
GET /heroes - Retrieve all heroes
GET /heroes/:id - Retrieve a single hero by ID
Powers
GET /powers - Retrieve all powers
GET /powers/:id - Retrieve a single power by ID
PATCH /powers/:id - Update a power description (min. 20 characters)
Hero Powers
POST /hero_powers - Assign a power to a hero
Requires hero_id, power_id, and strength (Strong, Weak, or Average)
Testing the API
Use Postman or curl to test the API endpoints.

Example PATCH request to update a power:

curl -X PATCH http://127.0.0.1:5000/powers/1 \
     -H "Content-Type: application/json" \
     -d '{"description": "Updated power description."}'
Troubleshooting
If flask db init fails due to an existing migrations folder, delete it and try again.
If port 5000 is in use, stop any existing Flask processes using:
lsof -i :5000
kill <PID>
License
This project is licensed under the MIT License.