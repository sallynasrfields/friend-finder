# friend-finder
An express based website used to link friends with other friends of similar nature.

## How to Use This App.
1. Enter "npm Install" into terminal.
2. Enter "npm start" into terminal.
3. Navigate to localhost:8080 in web browser.
4. Click on survey.
5. Answer all questions.
6. The name and picture of your **Best Match** will be displayed after clicking "Submit".
7. View database of survey results by clicking api/friends link.
7. Once done with app, you can stop the server, "ctrl-c"



## How it Works

...This is an example of a full stack application that uses the Express npm package to perform AJAX calls to a local server, processing JSON, URLs, and text through the body-parser npm package, with routes fetching HTML documents through the usage of the Path npm package. The main components of this application are: 
1. A server.js that listens for AJAX calls. This server:
* requires "express" npm package,
* requires "body-parsar" npm package,
* requires a htmlRoutes.js file,
* requires an apiRoutes.js file.

2. An htmlRoutes.js file that:
* requires "path" npm package,
* makes an AJAX "get" call (enabled by express) for the server to get home.html based on speficied urls,
* makes an AJAX "get" call (enabled by express) for the server to get survey.html when "Survey" button is clicked.

3. A survey.html page that has an "on click" function that:
* performs a data validation to make sure that all questions were answered,
* stores the survey results in a local variant, surveyResults,
* makes a call to an AJAX post function in apiRoutes.js. This call sends the surveyResults to the AJAX post, which then calculates the best match and sends it back to the caller. The caller then captures the name and picture of the best match in local variants, which then are displayed in a modal.

4. And finally, an apiRoutes.js file that:
* requires data/friends.js and assigns content to local variant, friendsData,
* makes an AJAX "get" call for the server to get friendsData when user navaigates to "/api/friends",
* makes an AJAX "post" call that first stores the surveyResults received in a local variable, then identifies the best match, sends it back to the caller, then finally adds the new set of friend data to the local variant, friendsData.


