# friend-finder
An express based website used to link friends with other friends of similar nature.

## How to use this app.
1. NPM Install
2. NPM Start
3. navigate to localhost:8080 in web browser
4. Click on survey
5. Answer all questions
6. The name and picture of your **Best Match** will be displayed after clicking "Submit"



## How it was built.

This is an example of a full stack application that uses the Express npm package to perform AJAX calls to a local server, processing JSON, URLs, and Text through the body-parser npm package, with routes fetching HTML documents through the usage of the Path npm package. The main components of this application are 
1. a server (server.js) that listens for AJAX calls. This server:
* requires Express npm package
* requires body parsar npm package
* requires a htmlroutes.js files
* requires a apiroutes.js file

2. An htmlRoutes.js file that:
* requires path npm package
* makes an AJAX "get" call (enabled by express) for the server to get home.html when based on speficied url
* makes an AJAX "get" call (enabled by express) for the server to get survey.html when survey button is clicked

3. A Survey.html page that:
* makes an AJAX call to post survey results to a location on the server, /api/friends, receives the best match from an AJAX POST function in the file apiRoutes.js, then displays the name and picture of the best match.

4. An apiRoutes.js file that:
* requires data/friends.js and assigns content to local variant, friendsData.
* makes an AJAX "get" call for the server to get friendsData when user navaigates to /api/friends.
* makes an AJAX "post call that first stores the surveyResults received in a local variable, then identifies the best match, sends it back to the caller, then finally adds the new set of friend data to the local variant, friendsData.



