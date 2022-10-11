# rest-api-exercise

Creating a new Actor

request:
POST http://api.movieapp.com/actors HTTP/1.1

{
  "name": "Brad Pitt", 
  "bio": "William Bradley Pitt (born December 18, 1963) is…", 
  "birthday": "1963-12-18", 
  "deathday": null, 
  "gender": 2, 
  "popularity": 9.93
}

response:
HTTP/1.1 201 Created
Location: /actors/283

{
  "id": 283, 
  "name": "Brad Pitt", 
  "bio": "William Bradley Pitt (born December 18, 1963) is…", 
  "birthday": "1963-12-18", 
  "deathday": null, 
  "gender": 2, 
  "popularity": 9.93
}
