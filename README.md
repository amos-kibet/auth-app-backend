## Install dependencies specified in package.json, from root directory

    npm install

## Create a .env file from root directory

    Create environment variables as described in .env.sample file

## Run the app

    npm start

## Testing API Base Endpoint

### Request

`GET /`

    curl -i -H 'Accept: application/json' http://localhost:8080/

### Response

    HTTP/1.1 200 OK
    X-Powered-By: Express
    Access-Control-Allow-Origin: http://localhost:3000
    Vary: Origin
    Content-Type: application/json; charset=utf-8
    Content-Length: 42
    ETag: W/"2a-mDGgOxXLQHH9egnM2CtgQRnQWrw"
    Date: Mon, 02 May 2022 01:41:33 GMT
    Connection: keep-alive
    Keep-Alive: timeout=5

    {"message":"Welcome to Auth App Backend."}%

## Sign Up

### Request

`POST /api/auth/signup/`

    curl -i -H 'Accept: application/json' -d 'username=John&email=johndoe@email.com&password=1234' http://localhost:8080/api/auth/signup

### Response

    HTTP/1.1 200 OK
    X-Powered-By: Express
    Access-Control-Allow-Origin: http://localhost:3000
    Vary: Origin
    Access-Control-Allow-Headers: x-access-token, Origin, Content-Type, Accept
    Content-Type: application/json; charset=utf-8
    Content-Length: 47
    ETag: W/"2f-ycIOj/6kXGxPaEoiW5+ikfXgO5w"
    Date: Mon, 02 May 2022 01:47:20 GMT
    Connection: keep-alive
    Keep-Alive: timeout=5

    {"message":"User was registered successfully!"}%

## Sign In Before Email Verification

### Request

`POST /api/auth/signin/`

    curl -i -H 'Accept: application/json' -d 'username=John&email=johndoe@email.com' http://localhost:8080/api/auth/signin

### Response

    HTTP/1.1 401 Unauthorized
    X-Powered-By: Express
    Access-Control-Allow-Origin: http://localhost:3000
    Vary: Origin
    Access-Control-Allow-Headers: x-access-token, Origin, Content-Type, Accept
    Content-Type: application/json; charset=utf-8
    Content-Length: 56
    ETag: W/"38-R2O7XZJ4o0WteOFrN9xZd+7Nh38"
    Date: Mon, 02 May 2022 01:53:43 GMT
    Connection: keep-alive
    Keep-Alive: timeout=5

    {"message":"Pending Account. Please Verify Your Email!"}%

## Sign In After Email Verification

### Request

`POST /api/auth/signin/`

    curl -i -H 'Accept: application/json' -d 'username=John&email=johndoe@email.com' http://localhost:8080/api/auth/signin

### Response

#### TODO: Edit once Nodemailer is able to send confirmation code

    HTTP/1.1 401 Unauthorized
    X-Powered-By: Express
    Access-Control-Allow-Origin: http://localhost:3000
    Vary: Origin
    Access-Control-Allow-Headers: x-access-token, Origin, Content-Type, Accept
    Content-Type: application/json; charset=utf-8
    Content-Length: 56
    ETag: W/"38-R2O7XZJ4o0WteOFrN9xZd+7Nh38"
    Date: Mon, 02 May 2022 01:53:43 GMT
    Connection: keep-alive
    Keep-Alive: timeout=5

    {"message":"Pending Account. Please Verify Your Email!"}%

## Get a specific User

### Request

`GET /api/auth/confirm/:confirmationCode`

    curl -i -H 'Accept: application/json' http://localhost:8080/api/auth/confirm/:confirmationCode

### Response

#### TODO: Edit once Nodemailer is able to send confirmation code

    HTTP/1.1 200 OK
    X-Powered-By: Express
    Access-Control-Allow-Origin: http://localhost:3000
    Vary: Origin
    Access-Control-Allow-Headers: x-access-token, Origin, Content-Type, Accept
    Content-Type: application/json; charset=utf-8
    Content-Length: 47
    ETag: W/"2f-ycIOj/6kXGxPaEoiW5+ikfXgO5w"
    Date: Mon, 02 May 2022 01:47:20 GMT
    Connection: keep-alive
    Keep-Alive: timeout=5

    {"message":"User was registered successfully!"}%
