# Business Application Project | Group 1

## Description

This repository contains the source code of the business application developed by Group 1 as part of the Enterprise Application Development course.

## Context

This application was commissioned by a fictional client (professor). The request was made in the form of a tender, to which we responded with a detailed specification document. This specification document is available in the `docs` folder. We used this specification document as the basis for developing the application.

We started by designing the application, creating use case diagrams, class diagrams, sequence diagrams, and deployment diagrams. These diagrams are available in the `docs` folder. To develop the application, we used Jakarta EE (Java EE), which is available in the `src` folder. An accompanying web application was developed using Vanilla JS, HTML, and CSS, and it is available in the `webapp` folder.

## Installation

### Prerequisites

- Java (JDK 11 or higher)
- NodeJS (v14.15.4 or higher)

### Installation Steps

1. Clone the repository
```bash
git clone https://github.com/cdhaeyere/2BIN-Q2-PAE.git
```
2. Launch the Java application from the IDE of your choice
3. Start the web application with NodeJS
    - Navigate to the `webapp` folder
    ```bash
    cd webapp
    ```
    - Install dependencies
    ```bash
    npm install
    ```
    - Run the application
    ```bash
    npm start
    ```
4. Visit http://localhost:3000 to access the web application

## Endpoints

### 1) Auth
| URI                 | Méthode HTTP | Auths? | Opération                                                                |
|---------------------|--------------|--------|--------------------------------------------------------------------------|
| **/auths/login**    | POST         | No     | READ ONE : Logs a user in and returns the token with the user.           |
| **/auths/register** | POST         | No     | CREATE ONE : Registers a user and returns the token with the user.       |
| **/auths/user**     | GET          | JWT    | READ ONE : Returns the user associated with the token stored in browser. | 

### 2) Users
| URI                               | Méthode HTTP | Auths? | Opération                                                                             |
|-----------------------------------|--------------|--------|---------------------------------------------------------------------------------------|
| **/users**                        | GET          | JWT    | READ ALL : Returns all users.                                                         |
| **/users/{idUser}/promote**       | PATCH        | JWT    | PATCH ONE : Update the user role to helper or manager.                                |  
| **/users/{idUser}/objects**       | GET          | JWT    | READ ALL : Returns all the objects of a given user.                                   |
| **/users/{idUser}**               | GET          | JWT    | READ ONE : Returns the user associated with the given id.                             |
| **/users/{idUser}/notifications** | GET          | JWT    | READ ALL : Returns a list of all the user notifications associated with the given id. |
| **/users/{idUser}/edit**          | PATCH        | JWT    | PATCH ONE : Modifies the user associated with the given id.                           |

### 3) Objects
| URI                        | Méthode HTTP | Auths? | Opération                                                                              |
|----------------------------|--------------|--------|----------------------------------------------------------------------------------------|
| **/objects**               | GET          | JWT    | READ ALL : Returns all the objects.                                                    |
| **/objects/home**          | GET          | No     | READ ALL : Returns all the home page objects.                                          |
| **/objects/{id}**          | GET          | No     | READ ONE : Returns the object associated with the given id.                            |
| **/objects/proposed**      | GET          | JWT    | READ ALL : Returns all the objects with the "PROPOSED" status.                         |
| **/objects**               | POST         | No     | CREATE ONE : Creates an object with the "PROPOSED" status.                             |
| **/objects/{id}/edit**     | PATCH        | JWT    | PATCH ONE : Modifies the object associated with the given id.                          |
| **/objects/{id}/accept**   | PATCH        | JWT    | PATCH ONE : Modifies the object associated with the given id to the "ACCEPTED" status. |
| **/objects/{id}/refuse**   | PATCH        | JWT    | PATCH ONE : Modifies the object associated with the given id to the "REFUSED" status.  |
| **/objects/{id}/workshop** | PATCH        | JWT    | PATCH ONE : Modifies the object associated with the given id to the "WORKSHOP" status. |
| **/objects/{id}/shop**     | PATCH        | JWT    | PATCH ONE : Modifies the object associated with the given id to the "SHOP" status.     |
| **/objects/{id}/onsale**   | PATCH        | JWT    | PATCH ONE : Modifies the object associated with the given id to the "ON_SALE" status.  |
| **/objects/{id}/sell**     | PATCH        | JWT    | PATCH ONE : Modifies the object associated with the given id to the "SOLD" status.     |
| **/objects/{id}/remove**   | PATCH        | JWT    | PATCH ONE : Modifies the object associated with the given id to the "REMOVED" status.  |

### 4) Object Types
| URI                          | Méthode HTTP | Auths? | Opération                                     |
|------------------------------|--------------|--------|-----------------------------------------------|
| **/objectTypes**             | GET          | No     | READ ALL : Returns all the object types.      |


### 5) Dashboard
| URI                          | Méthode HTTP | Auths? | Opération                                     |
|------------------------------|--------------|--------|-----------------------------------------------|
| **/dashboard**               | GET          | JWT    | READ ALL : Returns all the dashboard data.    |

### 6) Availabilities

| URI                 | Méthode HTTP | Auths? | Opération                                  |
|---------------------|--------------|--------|--------------------------------------------|
| **/availabilities** | GET          | No     | READ ALL : Returns all the availabilities. |
