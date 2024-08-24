# School Management API

This project is a simple RESTful API for managing school data. It allows users to add new schools to a database and retrieve a list of schools sorted by proximity to a given location.

## Live URL

The API is deployed and live at:
[https://school-management-api-1-iecw.onrender.com](https://school-management-api-1-iecw.onrender.com)

## API Endpoints

### 1. Add School

- **Endpoint**: `/addSchool`
- **Method**: `POST`
- **Description**: Adds a new school to the database.
- **Request Body** (JSON):
  ```json
  {
      "name": "ABC School",
      "address": "123 Main St",
      "latitude": 40.7128,
      "longitude": -74.0060
  }


Response:
{
    "message": "School added successfully",
    "schoolId": 1
}


### 2. List School
Endpoint: /listSchools
Method: GET
Description: Retrieves a list of schools sorted by proximity to the given latitude and longitude.
Query Parameters:
latitude: User's latitude
longitude: User's longitude
Example request:
https://school-management-api-1-iecw.onrender.com/listSchools?latitude=40.7128&longitude=-74.0060
Response:
[
    {
        "id": 1,
        "name": "ABC School",
        "address": "123 Main St",
        "latitude": 40.712799072265625,
        "longitude": -74.00599670410156
    },
    {
        "id": 6,
        "name": "ABC School",
        "address": "123 Main St",
        "latitude": 40.712799072265625,
        "longitude": -74.00599670410156
    },
    {
        "id": 8,
        "name": "ABC School",
        "address": "123 Main St",
        "latitude": 40.712799072265625,
        "longitude": -74.00599670410156
    },
    {
        "id": 7,
        "name": "Kendriya vidyalaya",
        "address": "456 Elm St",
        "latitude": 34.05220031738281,
        "longitude": -118.24369812011719
    },
    {
        "id": 2,
        "name": "Aster public school",
        "address": "delhi",
        "latitude": 45.900001525878906,
        "longitude": -21
    },
    {
        "id": 5,
        "name": "Aster public school",
        "address": "delhi",
        "latitude": 100,
        "longitude": 90
    },
    {
        "id": 3,
        "name": "Aster public school",
        "address": "delhi",
        "latitude": 19,
        "longitude": -28
    },
    {
        "id": 4,
        "name": "Aster public school",
        "address": "delhi",
        "latitude": 255,
        "longitude": -289
    }
]


FOR LOCAL SETUP:
Prerequisites
-Node.js
-MySQL


Steps:
1. Clone the repository:
git clone https://github.com/your-username/school-management-api.git
cd school-management-api
2. npm install
3. Set up environment variables:
DB_HOST=sql12.freesqldatabase.com
DB_USER=sql12727589
DB_PASSWORD=Eq2gZtirDt
DB_NAME=sql12727589
DB_PORT=3306

4. CREATE TABLE schools (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    address VARCHAR(255) NOT NULL,
    latitude FLOAT NOT NULL,
    longitude FLOAT NOT NULL
);

Use phpmyadmin: https://www.phpmyadmin.co/
Login using sql12.freesqldatabase.com as server.

5.Start the server
node app.js

6. Test the API
POST /addSchool
GET /listSchools


-----------------------------------------------------------


