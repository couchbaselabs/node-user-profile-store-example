# User Profile Store Example

An example of how to create a user profile store with NoSQL and Node.js. The demo shows how to create user accounts and gain access to those accounts via a token.

## Running the Application

With Node.js installed and the project downloaded, execute the following:

```
npm install
npm start
```

The application will be served with Nodemon at http://localhost:3000. Make sure to update the database configuration at the top of the **app.js** file.

## API Endpoints

**POST /account**

```
request_body: {
    "firstname": string,
    "lastname": string,
    "email": string,
    "password": string
}

response: {
    "cas": numeric
}
```

**POST /login**

```
request_body: {
    "email": string,
    "password": string
}

response: {
    "sid": string
}
```

**GET /account**

```
request_headers: {
    "Authorization": "bearer {sid}"
}

response: {
    "firstname": string,
    "lastname": string,
    "email": string,
    "type": string
}
```

**POST /blog**

```
request_headers: {
    "Authorization": "bearer {sid}"
}

request_body: {
    "title": string,
    "content": string
}

response: {
    "type": string,
    "pid": string,
    "title": string,
    "content": string,
    "timestamp": numeric
}
```

**GET /blogs**

```
request_headers: {
    "Authorization": "bearer {sid}"
}

response: [
    {
        "type": string,
        "pid": string,
        "title": string,
        "content": string,
        "timestamp": numeric
    }
]
```

## Resources

Written Tutorial - https://blog.couchbase.com/creating-user-profile-store-with-node-js-nosql-database/
Video Tutorial - https://blog.couchbase.com/develop-user-profile-store-session-store-node-js-video/
