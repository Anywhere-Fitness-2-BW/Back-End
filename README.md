# Anywhere Fitness

## Table of contents

- **[Overview](#overview)**<br>
- **[API Endpoints](#api-endpoints)**<br>

## <a name="overview"></a>Overview

AnywhereFitness is the all-in-one solution to meet your “on-location” fitness class needs.
AnywhereFitness makes it painless for Instructors and Clients alike to hold and attend Fitness
classes wherever they might be held.

## <a name="api-endpoints"></a>API endpoints

### **_Authentication (for login)_**

| Method        | Endpoint           | Body (required)                       | Body (optional) | Notes                                                                                                                                                   |
| ------------- | ------------------ | ------------------------------------- | --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| register POST | /api/auth/register | name, email, username, password, role | N/A             | Creates a new user object in the database. Date has to string in "04/19/2020" format. Duration is a float and signedUp is a boolean(false as a default) |
| login POST    | /api/auth/login    | username, password                    | N/A             | Returns a welcome message and the JSON Web Token.                                                                                                       |

### **_Additional athunetication for Instructor_**

| Method               | Endpoint                 | Body (required)                                                                     | Body (optional) | Notes                                      |
| -------------------- | ------------------------ | ----------------------------------------------------------------------------------- | --------------- | ------------------------------------------ |
| Add class POST       | /api/auth/instructor     | name, instructor_name, type, intensity,location, date, max_size, duration, signedUp | N/A             | Creates a new class object in the database |
| Update Class PUT     | /api/auth/instructor/:id | any of the field                                                                    | N/A             | Updates the class with given Id            |
| Removes Class DELETE | /api/auth/instructor/:id | any of the field                                                                    | N/A             | Deletes the class with given Id            |

### **_Endpoints for the Users_**

| Method                | Endpoint                    | Body (required) | Body (optional) | Notes                                     |
| --------------------- | --------------------------- | --------------- | --------------- | ----------------------------------------- |
| get classes GET       | /api/auth/users/classes     | N/A             | N/A             | Fetches all the classes from the database |
| get classed by Id GET | /api/auth/users/classes/:id | N/A             | N/A             | Fetches the class with given Id.          |
