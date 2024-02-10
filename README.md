# Node.js Application Example

## Run uncontained

Setup:

```bash
$ cd src
$ npm install
```

Start a PostgreSQL database and create the tables:

```bash
$ docker run -it -e "POSTGRES_HOST_AUTH_METHOD=trust" -p 5432:5432 postgres
$ npm run migrate
```

Start application:

```bash
$ npm start
```

## API Usage

- `GET /persons/all` retrieve all persons in the addressbook
- `GET /persons/1` retrieve person with id 1
- `PUT /persons/` add a person to the addressbook
- `DELETE /persons/1` delete person with id 1

Example:

```bash
curl -X PUT http://localhost:3000/persons -H 'Content-Type: application/json' -d '{"id": 1, "firstName": "David", "lastName": "Bowie"}'
```

```bash
curl -X GET http://localhost:3000/persons -H 'Content-Type: application/json'
{"firstName":"David","lastName":"Bowie","id":1,"updatedAt":"2023-04-30T22:44:29.115Z","createdAt":"2023-04-30T22:44:29.115Z"}
```
