Before running the application, create databases "wiredcraft" and "wiredcraft_test" in local
mysql

To get dependencies:
Run 'go get'

To build the exectuable:
Run 'go build -o wiredcraft_test'

To run the executable:
Run './wiredcraft_test'
The server will be running on localhost:8080

To test:
Run 'go test'

**************************************************

API endpoints:

All API endpoints are under /api namespace.
User get, update, and delete endpoints should be requested with "Authorization" header. The value of the header should be "bearer " + token received from /login endpoint.

User model:
```
{
  email string
  password string
  name string
  dob string
  address string
  description string
  createdAt string
}
```

**Create a user**
Endpoint: ```POST /user```
Send payload as json string in body:
```
{
  "email": "boris@uk.com",
  "password": "test",
  "name": "Boris",
  "dob": "1950-01-01T12:00:00Z",
  "address": "London",
  "description": "UK foreign minister"
}
```

###########################################################################
**User login**
Endpoint: ``` POST /login```
Send payload as form data:
email: boris@uk.com
password: test

###########################################################################

**Retrieve individual user**
Endpoint: ```GET /user/:id```, where ```:id``` is the id of the user we want to retrieve

###########################################################################

**Retrieve all users**
Endpoint: ```GET /users```
Params: page(default: 1),
        per_page(default: 10)

###########################################################################

**Update a user**
Endpoint: ```PUT /user/:id```, where ```:id``` is the id of the user we want to update
Send payload as json string in body:
```
{
  "address": "Bishkek"
}
```

###########################################################################

**Delete a user**
Endpoint: ```DELETE /user/:id```, where ```:id``` is the id of the user we want to delete



