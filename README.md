# lab2_74535_Ma

Full Name: Gao Erwann
Student Id: 74535
Requirements:

1. Movie screen:
   1.1. Create a Movie class with the structure specified in movie.json (Done)
   1.2. Obtain and fill data (minimum of 4 movies) (Done)
   1.2.1. Obtain relevant movie data from Vue (https://www.myvue.com/cinema/dublin/whats-on) or your favourite provider and add data credits at the bottom of the app (partially Done)
   1.2.2. Generate a random number between 0 and 15 for each movie and assign to seats_remaining (Done)
   1.2.3. Start with an initial default seats_selected value of 0 for all movies (Done)
   1.2.4. You shall fill random URLs for images from pixabay or other free image providers to begin with (Done)
   1.4. If any seats are selected, show how many seats are selected and hide remaining seats (partially Done)
2. Seat selection feature:
   2.1. Clicking any item (anywhere on the item) on the movie screen should open a new MovieActivity, refer to movie*activity*\*.jpg (Done)
   2.2. Add plus and minus icons, show seats_selected in the middle (Done)
   2.3. On click plus/minus, update both seats_selected and seats_remaining for that movie (Done)
   2.4. Add validation, when 0 seats selected minus is disabled, when 0 seats remaining plus is disabled (Done)
   2.5. When back is pressed, the selected seats are retained and reflected in the screen. (Hint: If you don’t see any updates, call adapter notifyItemChanged as soon as you return to the screen activity) (Done)

The devlopment of this app went pretty well but I still had got some struggle to make the update of my list of movie work.
To do so, I first tried to use notifyItemChanged with Adapter but I think that this method wasn't really compatible with Jetpack Compose. I then tried to use mutable State, I spent a lot of time trying to make it works but I succeeded.I first tried to use the method mutableStateOf on the seats_remaining and seats_selected variable but I had to recreate a movie from the previous with the new value in the composable of the activity which caused some bug of conflicting modification when I added the Basket Screen And even though the screen was updated, the dataset wasn't. I then managed to find the solution which is to use the ImmutableStateList method, I passed my ImmutableStateList has argument through all the function until the 3 that actually modifies the list.
I still create new Object but this time It's only when I need to update the data beacause of change. I am so deleting the old movie to add the updated one which trigger the ImmutableStateList that allows to update the data set and recompose the Screen. The rest of the project where quite easy and even though I struggled a lot, I had a lot of fun making this project.
Concerning the routing, the tutorial on the Lecturer's Youtube Channel was easily understandable so I manage to do It very fastly, I am actually surprised that It worked that well at the first try.
I learn in the process of the creation of this app how the routing of an Android Application is done. I also learned a way of update data set and recompose screen in real time when modify data, this migh not be the best as It need to create a new instance of an object just to change increment 1 parameter. I also retained that It is better to read slowly and quietly the documentation when I am blocked than going to plenty of different website and forum that that never use exact same tool in the same version that me not always say the same thing to the same problem.
