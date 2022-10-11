# rest-api-exercise

**1. General Movie CRUD**

**a. Creating a new movie**

**request:**

POST http://api.movieapp.com/movies HTTP/1.1

{"movies":
[
{<br>
  "title": "movie name", <br>
  "plot": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "poster": "1963-12-18", <br>
  "budget": 1000000, <br>
  "revenue": 150000, <br>
  "genres": ["Comedy","Drama"]<br>
  }
  ]
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
{
"actors":
[
{<br>
  "id": 123
  "name": "Brad Pitt", <br>
  "bio": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "birthday": "1963-12-18", <br>
  "deathday": null, <br>
  "gender": 2, <br>
  "popularity": 9.93<br>
}
]
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

**3. Get actors of a specific movie.**

**request:**

GET http://api.movieapp.com/actors?movie=123&limit=20&offset=0 HTTP/1.1

**response:**
HTTP/1.1 200 OK
{[actors]}

**4. Add an actor to a specific movie.**

**request:**

POST http://api.movieapp.com/movies/actors?actor=123 HTTP/1.1

**response:**

HTTP/1.1 204 modified 
Location: /actors/123

{
"id":123,
...
}

**5. Remove an actor from a specific movie.**

**request:**

DELETE http://api.movieapp.com/movies/actors?actor=123 HTTP/1.1

**response:**

HTTP/1.1 204 No Content


**6. Get the top 3 stars (most popular actors) of a specific movie**

**request:**

get http://api.movieapp.com/actors?movie=123&top=3 HTTP/1.1

**response:**

HTTP/1.1 200 OK
{
[players]
}


**7. Update a specific movie’s revenue.**

**request:**

PUT http://api.movieapp.com/movies/123 HTTP/1.1

{<br>
  "title": "movie name", <br>
  "plot": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "poster": "1963-12-18", <br>
  "budget": 1000000, <br>
  "revenue": 150000, <br>
  "genres": ["Comedy","Drama"]<br>
}

**response:**
HTTP/1.1 200 OK

{<br>
  "title": "movie name", <br>
  "plot": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "poster": "1963-12-18", <br>
  "budget": 1000000, <br>
  "revenue": 150000, <br>
  "genres": ["Comedy","Drama"]<br>
}


**8. Get the top 10 action movies.**

**request:**

GET http://api.movieapp.com/movies?cat=action&limit=10&offset=0 HTTP/1.1

**response:**

HTTP/1.1 200 OK

{[<br>
  "id": 283, <br>
  "name": "Brad Pitt", <br>
  "bio": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "birthday": "1963-12-18", <br>
  "deathday": null, <br>
  "gender": 2, <br>
  "popularity": 9.93<br>,
  ...]
}


**9. Get the drama movies of a specific actor.**

**request:**

GET http://api.movieapp.com/actors?movieCat=drama&limit=10&offset=0 HTTP/1.1

**response:**

HTTP/1.1 200 OK
{
"actors":[{},...]
}

**10. Get the top 3 most popular movies of a specific actor.**

**request:**

GET http://api.movieapp.com/movies?actor=123&top=3 HTTP/1.1
**response:**

HTTP/1.1 200 OK

**11. Create 5 actors in a single request.**

**request:**

POST http://api.movieapp.com/movies HTTP/1.1
{
actors:[{<br>
  "name": "Brad Pitt", <br>
  "bio": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "birthday": "1963-12-18", <br>
  "deathday": null, <br>
  "gender": 5, <br>
  "popularity": 9.93<br>
},
{<br>
  "name": "Brad Pitt", <br>
  "bio": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "birthday": "1963-12-18", <br>
  "deathday": null, <br>
  "gender": 5, <br>
  "popularity": 9.93<br>
},
{<br>
  "name": "Brad Pitt", <br>
  "bio": "William Bradley Pitt (born December 18, 1963) is…", <br>
  "birthday": "1963-12-18", <br>
  "deathday": null, <br>
  "gender": 5, <br>
  "popularity": 9.93<br>
}]
}
**response:**

HTTP/1.1 201 OK


