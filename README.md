# what-to-watch-backend
**REST API with movies for what-to-watch**

## THE ROUTES:

**GET /films**
Get the list of movies.

- Response status:
  - 200 ОК

Example:
- Request:
  - URL: GET /films

- Response:
  - Status: 200 OK
  - Body: array with structures of type Film

**GET /films/promo**
Get a promo movie.

- Response status:
  - 200 ОК

Example:
- Request:
  - URL: GET /films/promo

- Response:
  - Status: 200 OK
  - Body: structure of type Film

**GET /favourite**
Get a list of favourite movies.

- Response:
  - 200 ОК
  - 401 Unauthorized (in case of not authorized)

Example:
- Request:
  - URL: GET /favourite
  
- Response:
  - Status: 200 OK
  - Body: array with structures of type Film

**POST /favourite/: film\_id/: status**
It is changing a movie&#39;s favourite status. The body of the response contains the data of the film with the current state of the is\_favorite field.

- Parameters:
  - :film\_id — ID of the movie you want to remove/add to favourites
  - : status — possible values 1 or 0. 1 adds film to favourites, 0 removes
  
- Response:
  - 200 ОК
  - 401 Unauthorized (in case of not authorized)

Example:
- Request:
  - URL: GET /favourite/42/1
  
- Response:
  - Status: 200 OK
  - Body: Film structure with the current state of the is\_favorite field

**GET /comments/: film\_id**
Get a list of comments for a movie by its id.

- Response:
  - 200 ОК
  - 400 Bad request

Example:
- Request:
  - URL: GET /comments/42

- Response:
  - Status: 200 OK
  - Body: array with structures of type Film

**POST /comments/: film\_id**
Post a new comment to a movie by its id.

- Response:
  - 200 ОК
  - 400 Bad request
  - 401 Unauthorized (in case of not authorized)

Example:
- Request:
  - URL: POST /comments/42
  - Body: structure of type CommentPost

- Response:
  - Status: 200 OK
  - Body: array with structures of type Film

**POST /login**
Authenticate the user on the server. If the request is successful, the token is written into the cookie, by which authorization is done later. If authorization on the server fails, then a 401 error is returned for requests to private parts of the site.

- Response:
  - 200 ОК
  - 400 Bad request

Example:
- Request:
  - URL: POST /login
  - Body: structure of type User

- Response:
  - Status: 200 OK
  - Body: structure of type AuthInfo

**GET /login**
Check user authorization status.

- Response:
  - 200 ОК
  - 401 Unauthorized (in case of not authorized)

Example:
- Request:
  - URL: GET /login

- Response:
  - Status: 200 OK
  - Body: structure of AuthInfo

- Response:
  - 200 ОК
  - 401 Unauthorized (in case of not authorized)
