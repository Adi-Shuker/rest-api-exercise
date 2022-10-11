# rest-api-exercise

**1. General Movie CRUD**

**a. Creating a new movie**

**request:**

POST http://api.movieapp.com/movies HTTP/1.1

{<br>
  "title": "movie name", <br>
  "plot": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "poster": "1963-12-18", <br>
  "budget": 1000000, <br>
  "revenue": 150000, <br>
  "genres": ["Comedy","Drama"]<br>
}

**response:**

HTTP/1.1 201 Created
Location: /movies/123

{<br>
  "id": 123
  "title": "movie name", <br>
  "plot": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "poster": "1963-12-18", <br>
  "budget": 1000000, <br>
  "revenue": 150000, <br>
  "genres": ["Comedy","Drama"]<br>
}

**b. reading movie**

**request:**

get http://api.movieapp.com/movies/123 HTTP/1.1


**response:**

HTTP/1.1 200 OK

{<br>
  "id": 283, <br>
  "name": "Brad Pitt", <br>
  "bio": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "birthday": "1963-12-18", <br>
  "deathday": null, <br>
  "gender": 2, <br>
  "popularity": 9.93<br>
}

**c. update movie**

**request:**

PUT http://api.movieapp.com/movies/123 HTTP/1.1

{<br>
  "title": "movie name", <br>
  "plot": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "poster": "1963-12-18", <br>
  "budget": 1000000, <br>
  "revenue": 150000, <br>
  "genres": ["Comedy"]<br>
}

**response:**

HTTP/1.1 200 OK
Location: /actors/283

{<br>
  "id": 123
  "title": "movie name", <br>
  "plot": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "poster": "1963-12-18", <br>
  "budget": 1000000, <br>
  "revenue": 150000, <br>
  "genres": ["Comedy"]<br>
}

**d. delete movie**

**request:**

DELETE http://api.movieapp.com/movies/123 HTTP/1.1

**response:**

HTTP/1.1 204 No Content

**2. General Actor CRUD**

**a. Creating a new Actor**

**request:**

POST http://api.movieapp.com/actors HTTP/1.1

{<br>
  "name": "Brad Pitt", <br>
  "bio": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "birthday": "1963-12-18", <br>
  "deathday": null, <br>
  "gender": 2, <br>
  "popularity": 9.93<br>
}

**response:**

HTTP/1.1 201 Created
Location: /actors/123

{<br>
  "id": 123
  "name": "Brad Pitt", <br>
  "bio": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "birthday": "1963-12-18", <br>
  "deathday": null, <br>
  "gender": 2, <br>
  "popularity": 9.93<br>
}

**b. reading movie**

**request:**

get http://api.movieapp.com/actors/123 HTTP/1.1


**response:**

HTTP/1.1 200 OK

{<br>
  "id": 123
  "name": "Brad Pitt", <br>
  "bio": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "birthday": "1963-12-18", <br>
  "deathday": null, <br>
  "gender": 2, <br>
  "popularity": 9.93<br>
}

**c. update movie**

**request:**

PUT http://api.movieapp.com/actors/123 HTTP/1.1

{<br>
  "name": "Brad Pitt", <br>
  "bio": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "birthday": "1963-12-18", <br>
  "deathday": null, <br>
  "gender": 5, <br>
  "popularity": 9.93<br>
}

**response:**

HTTP/1.1 200 OK
Location: /actors/123

{<br>
  "id": 123
  "name": "Brad Pitt", <br>
  "bio": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "birthday": "1963-12-18", <br>
  "deathday": null, <br>
  "gender": 5, <br>
  "popularity": 9.93<br>
}

**d. delete movie**

**request:**

DELETE http://api.movieapp.com/actors/123 HTTP/1.1

**response:**

HTTP/1.1 204 No Content
