## ASP.NET Web Api 2 (REST):

- vs -> project properties -> web -> don't open a page [this is for testing just the API]
- after build and start the project: in postman -> GET http://localhost:6600/api/values
- extentions: open command, add new file [shift+F2 to add a file]

- request process: GET req http://localhost:6600/api/values come -> /api/values is the route -> search all routes for match -> match it on action in a controller -> execute the action -> the result from the action return as a response
- status codes: 
  - 200: all successes.
    - 200 = OK (it worked)
    - 201 = Created
    - 202 = Accepted
  - 300: request was successful but something's changed.
    - 302 = Found
    - 304 = Not Modified (in case of caching)
    - 307 = Temp Redirect
    - 308 = Perm Redirect
  - 400: you requested something incorrectly.
    - 400 = Bad Request (you did bad)
    - 401 = Unauthorized
    - 403 = Forbidden
    - 404 = Not Found
    - 405 = Method Not Allowed
    - 409 = Conflict
  - 500: reporting that the server failed (server error).
    - 500 = Internal Server Error (we did bad)

- IHttpActionResult return type: allow us to return payload and status code
- in pmc: update-database -> to enforce all migrations happen

- must use model when dealing with data insted of entities
- add AutoMapper to map fields as conventions
  - add CampMappingProfile.cs for mapping process config
  - register it as a single instance in the IoC AutoFac container 

- Contract Serilization:
  - if we want to return the object properties in camel case insted of pascal case for using javascript must use: 'Contract Serilization'
  - by default in web api we serializing in json, to enforce to return another type: in the req header -> key: Accept, value: text/xml
  - use this in WebApiConfig: config.Formatters.JsonFormatter.SerializerSettings.ContractResolver = new CamelCasePropertyNamesContractResolver();

- add Route and RoutePrefix attribute
- if we put the type name before the prop name AutoMapper by convention will map it's value 'LocationVenueName, LocationAddress1, ...'
