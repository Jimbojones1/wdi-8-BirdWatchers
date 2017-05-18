## Homework: Put a Server in your pipe and smoke it

(REPO LINK FORK THIS SHIT)[https://github.com/ga-chicago/Sinatra-Animal-Reps]
**Strangers in the SERVERS**

1. It is time to build the cutest server ever - the `small_animals` server! Place this in a new folder in `sinatraAnimals`
2. Create a brand new, small Sinatra app.
3. Inside of your `app.rb`, you need to create a few routes...
  * '/' - This should return a Hash turned into JSON with the following keys: `:name` and `:message
  * *Five* different routes mapped to the names of small animals - ie `/kitten` and `/puppy`
  * These five different routes should return a hash turned JSON with the following keys: `:name`, `:cuteness`, `:habitat`, `:picture_url`, and `:description`
5. Test and verify these routes render JSON in the browser.
6. **BONUS**: Add *ERB* views and then create a new `/views/json_test.erb`. Map it to a `router` and call each API call using  `$.ajax` to render the content using `console.log` or whatever else you choose maybe using jQuery to append the data?  

