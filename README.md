# IMDB-clone-app
Create a mini IMDB clone app. Use ONLY vanilla javascript, no libraries or frameworks allowed for Javascript (you can use any CSS framework like Bootstrap).  Refer to the question doc for more details:

**# HTML**
<!DOCTYPE html>
<html>
<head>
  <title>IMDB Clone</title>
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
</head>
<body>
  <div class="container">
    <h1 class="mt-4">Movie List</h1>
    <div id="movieList" class="mt-4"></div>
  </div>

  <script src="script.js"></script>
</body>
</html>

**#JavaScript (script.js)**
// Sample movie data
const movies = [
  { title: "The Shawshank Redemption", rating: 9.3, genre: "Drama" },
  { title: "The Godfather", rating: 9.2, genre: "Crime" },
  { title: "The Dark Knight", rating: 9.0, genre: "Action" },
  { title: "Pulp Fiction", rating: 8.9, genre: "Crime" },
  { title: "Fight Club", rating: 8.8, genre: "Drama" },
];

// Function to create movie cards
function createMovieCard(movie) {
  const card = document.createElement("div");
  card.className = "card mb-3";

  const cardBody = document.createElement("div");
  cardBody.className = "card-body";

  const title = document.createElement("h5");
  title.className = "card-title";
  title.textContent = movie.title;

  const rating = document.createElement("p");
  rating.className = "card-text";
  rating.textContent = `Rating: ${movie.rating}`;

  const genre = document.createElement("p");
  genre.className = "card-text";
  genre.textContent = `Genre: ${movie.genre}`;

  cardBody.appendChild(title);
  cardBody.appendChild(rating);
  cardBody.appendChild(genre);
  card.appendChild(cardBody);

  return card;
}

// Function to display movies
function displayMovies() {
  const movieList = document.getElementById("movieList");

  // Clear existing movie list
  movieList.innerHTML = "";

  // Create movie cards for each movie
  movies.forEach(function (movie) {
    const movieCard = createMovieCard(movie);
    movieList.appendChild(movieCard);
  });
}

// Display movies on page load
document.addEventListener("DOMContentLoaded", displayMovies);
