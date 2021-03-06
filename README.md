# friend-finder
An express based website used to link friends with other friends of similar nature.

## How to Use This App
1. Enter "npm Install" into terminal to install all required npm packages locally.
2. Enter "npm start" into terminal to start the server. A message logged to the console will notify you that your server is "listening".
3. Navigate to localhost:8080 in web browser.
4. Click on "Survey".
5. Answer all questions.
6. The name and picture of your **Best Match** will be displayed after clicking "Submit".
7. View database of survey results by clicking api/friends link.
7. Once done with app, you can stop the server by entering the command, "ctrl-c", into the terminal.



## How it Works

This is an example of a full-stack application that uses the "express" npm package to perform AJAX calls to a local server, processing JSON, URLs, and text through the "body-parser" npm package, and processing HTML AJAX calls through the usage of the "path" npm package. The main components of this application are: 
1. A *server.js* file that, when started, listens for AJAX calls. This server:
* requires "express" npm package,
* requires "body-parsar" npm package,
* requires a htmlRoutes.js file,
* requires an apiRoutes.js file.

2. An *htmlRoutes.js* file that:
* requires "path" npm package,
* makes an AJAX "get" call (enabled by express) for the server to get home.html based on speficied urls,
* makes an AJAX "get" call (enabled by express) for the server to get survey.html when "Survey" button is clicked.

3. A *survey.html* file that has an "on click" function that:
* performs a data validation to make sure that all questions were answered,
* stores the survey results in a local variant, surveyResults,
* makes a call to an AJAX post function in apiRoutes.js. This call sends the surveyResults to the AJAX post, receives & captures the name and picture of the best match (sent from the AJAX post) in local variants, then finally displays the name and picture in a modal.

4. And finally, an *apiRoutes.js* file that:
* requires the file, data/friends.js, and assigns its contents (in the form of JSON) to local variant, friendsData,
* makes an AJAX "get" call (enabled by express) for the server to get friendsData when user navigates to "/api/friends",
* makes an AJAX "post" call (enabled by express) that first stores the surveyResults received in a local variable, then identifies the best match, sends it back to the caller, then finally adds the new set of surveyResults to the local variant, friendsData.


