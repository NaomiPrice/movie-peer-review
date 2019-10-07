# Weekend Challenge 12 - Saga Movies

## Instructions

Reviewing code is an important role developers play. We're going to practice reviewing code from others.

- Get the repo url from your partner
- Get your partner's project running on your computer
- Review the code from your partner and give relevant feedback
- Complete the Markdown section and submit that in the notes section on the assignment app. (Make sure you include who's code you reviewed.)

Practicing compassionate code reviews is important (you can learn more from this video on the topic: https://www.youtube.com/watch?v=Ea8EiIPZvh0 )



## Movies Page

- [x] Client side View that displays a list of movies (image, title, description)
- [x] View has ability to click on a single movie
- [x] Clicking on single movie goes to movie details view at `/details`

## Details Page

- [x] Detail view should show all detail data include all the genres for the given movie
- [x] Has Back to List which goes back to the Home Page
- [x] Has an Edit button which goes to the Edit Page

## Edit Page

- [x] View at route `/edit`
- [x] Assumes the selected movie id is in Redux
- [x] Display an input field for changing the movie title
- [x] Displays a textarea for changing the movie description
- [x] Cancel button, which should bring the user to the Details Page
- [ ] Save button, which should update the title and description in the database and bring the user to the Details Page

## General Tasks

- [x] Use Sagas for API requests to the server
- [x] Should have at least 15+ commits. 
- [ ] Use branches for features.
- [ ] Comment your code.
- [x] Update this README to include a description of the project in your own words.

## Stretch Goals

> NOTE: Copy/pasted from instructions

- [x] Display the current values in the input (title) and textarea (description) on the Edit Page
- [ ] Display all genres on movie list page. Research array_agg to make this possible.
- [ ] Move sagas and reducers out of your index.js and into separate files (ideally in src/redux/reducers and src/redux/sagas folders).
- [ ] Allow the user to refresh the details or edit page. The url for the details page would be something like /details/1 for movie with id of 1. Research react router params.
- [ ] Allow the user to add a genre to a movie.
- [ ] Allow the user to remove a genre from a movie.
- [ ] Only display the top 10 movies, and allow the user to search for movie titles with a search bar on the home page (you can do this on the client side or the server side, server side is a bigger stretch, but good practice).
- [ ] Create an Admin page. Add a link from the Home page to the Admin page. The page should initially display a login form (an input for username and an input for password). When the user enters the correct username (camera) and password (action), the page should display a form to add genres to the database, and a list of all of the genres with an x to remove them from the database. 

## Junction Table

Lots of student will forget to give you their junction table. Here is a common one:

```
-- JUNCTION DEFINITION

-- CREATE TABLE "movie_genre"

CREATE TABLE "movies_genres" (
  "id" SERIAL PRIMARY KEY,
  "movie_id" INT REFERENCES "movies" NOT NULL,
  "genre_id" INT REFERENCES "genres" NOT NULL
);

-- TEST DATA

INSERT INTO "movies_genres" ("movie_id", "genre_id")
VALUES (1,1), (1,3), (1,4), (2, 1), (3, 11), (3, 12);
```


## Portal-ready Markdown

```

---
| Functional Requirements | Complete? |
| --- | :---: |
| Junction table created to store genres per movie | yes |
| Initial Display shows all movies in a list, | yes |
| Initial Display shows all movie titles, descriptions, and images | no |
| Movies can be clicked on to go to their detail page | yes |
| Movie Detail Page displays movie image, title, description | yes |
| Movie Detail Page displays all genres for this movie | yes |
| Movie Edit Page allows the movie title to be updated | yes |
| Movie Edit Page allows the movie description to be updated | yes |
| Sagas used for calls to server | yes |

---
### Notes: It looked good! I also didn't display all the data on the front page - apparently we were suposed to - I liked how we did it:)
I noticed that if there isn't a genre assigned to a movie, the details won't display - you maybe could have done the map based on details rather than genre and still grabbed the info. 

Notes on items above.

---
| General Items | Complete? |
| --- | :---: |
| More than 15 git commits | yes |
| Updated SQL file with junction table name, schema, inserts | no |
| Code broken down into Components | yes |
| Commits are descriptive of the changes made or feature added | yes |
| Readme file updated | yes |
| Appropriate amount of code comments | no - not as descriptive of function |
| Code is consistently formatted | yes |
| Good use of Redux (where appropriate) | yes |
---
### Notes:
nice work!


```

