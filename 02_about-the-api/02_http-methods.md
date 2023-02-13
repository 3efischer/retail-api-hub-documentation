## HTTP methods

We are compliant with the standardized HTTP semantics and use the HTTP request methods `GET`, `POST`, `PUT`, `PATCH`, `DELETE` and `OPTIONS` throughout the API.

|  Method   |      CRUD       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| :-------: | :-------------: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|   `GET`   |      Read       | Retrieve either a single or a collection resource. Successful `GET` requests return `200 OK`. For a collection resource, `GET` requests also return `200 OK` if the collection is empty. If a single or collection resource is missing, the API returns `404 Not Found` or `410 Gone`.<br>In case of a `404 Not Found`, check the structure of your query and the name of the requested endpoint and resource.                                                                                                                                                                                                                                                           |
|  `POST`   |     Create      | Create a single resource on a collection resource endpoint. Successful `POST` requests either return `200 OK` if the resource already exists, or `201 Created` if a new resource was created. In case of `201 Created` the `Location` header of the response contains the URI of the new resource. The request returns `202 Accepted` after it was accepted but not yet completed. In exceptional cases the request returns `204 No Content` with a `Location` header containing the URI of the new resource.<br>In error cases the request returns `422 Unprocessable Entity` for semantically malformed or `400 Bad Request` for syntactically malformed requests. |
|  `PATCH`  |  Update/Modify  | Update parts of a single resource. Successful `PATCH` requests return `200 OK` with a response body, or `204 No Content` if a resource was updated.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|   `PUT`   | Update/Replace  | Update or replace an entire resource. Successful `PUT` requests return `200 OK` with a response body. The request returns `201 Created` if the resource was created, or `204 No Content` if a resource was updated.                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| `DELETE`  |     Delete      | Delete a resource. Successful `DELETE` requests usually return `204 No Content` without a response body. In rare cases, a delete request returns `200 OK`. Failed `DELETE` requests return `404 Not Found` if the resource cannot be found, or `410 Gone` if the resource has already been deleted before.                                                                                                                                                                                                                                                                                                                                                               |
| `OPTIONS` | Inspect Methods | Inspect the available HTTP methods of a given endpoint. `OPTIONS` responses usually contain either a comma-separated list of methods in the `Allow` header, or a structured list of link templates.                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |