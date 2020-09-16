# Final Project

## Movie Master
This is a mini IMDb web application which provides information about movies and webseries. 
This application provides information about a wide range of movies and webseries. A user can see the ratings provided by other users, trailers, get information about cast and crew of the movie. Application also provides detailed information about actors, like the birth name, birth date,  death date(if applicable), movies in which he/she has acted. Application also has link to wikipedia pages of respective movies/people.

## Watch video here
https://youtu.be/jHkq6WrelzU

## Usage
Create a user account to login to the site. Search for movies. keep track of movies watched, save movies in a wihlist

## Built With
Python 3.6, Django, HTML, Javascript, BeautifulSoup, IMDb API and WikiPY. Please Check the rquirements.txt for all the libraries installed.

## Home Page
Home page is visible to signees and non-signees. Home page contains a corosal with three images. I also contains a section for trailers of movies and web series. Each trailer shows the title, poster and length of the trailer of the movie/series.
The data on this page is populated from the index method in movies/views.py module.

## Search page
This page shows the search results based on the search query given by the user. IMDb's search_movie(self, title) method is used to produce the search results. The page contains link to the respective movie page of the results. 
The data on this page is populated from the searchMovie method in movies/views.py module.

## Top Rated Movies Page
This page contains list of 250 top rated movies. The data in this page is shown from 'top rated movies' page of IMDb website. The data from IMDB web page is obtained using webscrapping method using Beautifulsoup library. The data shown on this page is populated from top250Moviespage methon in movies/views.py module.

## Popular Movies Page
This page contains list of popular movies based on the IMDb user ratings. The data in this page is shown from 'Popular movies' page of IMDb website. The data from IMDB web page is obtained using webscrapping method using Beautifulsoup library. The data shown on this page is populated from popularMoviespage method in movies/views.py module.

## WishList Page
This is user data. The user can add movie to his wishlist for later reference. A user can have one wishlist and this wishlist is stored in the database along with the user details. User can not only add movie to the wishlist but can also keep track of number of times he/she has watched a movie. The link on 'Mark as watched' column will help in keeping track of number of times the movie has been watched. User can also delete the movie from the wishlist. 
The data on this page is obtained from addWishlist, updateWishlist methods in movies/views.py module
 ### DB details
 WishList model in movies app is used for storing the user wishlist data
 User model is used for storing the user related data 

## Trailers data 
This data is obtained using Youtube V3 API. Since there is a quota limit per userid on youtube, for the mass data of trailers datais obtained one-time and stored in Json file. and this Json data is loaded in trailer section everytime.
But in case of individual trailer shown on movie page, the data is obtained directly from youtube API without storing it on JSon file.
The data for this section is populted from getTrailers method in movies/helperMethods.py module


## Movie Page and Person Page Data
The data on this page is populated from getMovie and getPersonDetails methods respectively. The movie's page sshow the trailer of the movie and other data like IMDB ratings for the movie, year in whivh the movie was released, geners, plot of the movie, cast and crew of the movie.
While the person page shows the person details like, birth name, birthdate, deathdate(if applicable), movies in which he/she has acted/directed.
These pages also contain a link to thier respective wikipedia page.
To obtain the wiki URL of movies and person wikiPy reader module has been used. 
The data for this page is populated from getWiki mothod in movies/views.py module.

