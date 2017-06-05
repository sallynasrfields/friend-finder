# friend-finder
An express based website used to help people find friends with similar interests.

## How it works.

To use this website, the user must first fill out a survey of 10 questions. Once all of the questions are answered, the user must submit the survey. Results are sent to back-end server and are compared with the results of all other submissions. A best match is calculated, then returned back to the user in the form of a "Pop-up" message. For more information - user can also view survey results of all previous submission by navigating to the link "API Friends List" at the bottom of the survey page.


## How it was built.

This is an example of a full stack application that uses AJAX, Express and JSON to post data to server, process the data and display results back to the end user. The main components of this application is 1) a server (server.js) 2) two javascript files for routings (apiRoutings & htmlRoutings) 3) a javascript file to house the survey results in JSON (friends.js) 4) and two HTML files (home.html & survey.html).

### The Front End

The end-user graphical interface was created through the usage of html & bootstrap. To start with the user is introduced to the application through the home page. A button is placed on the home page that nagivates the user to the survey.

### The Ajax call
Logic on this page was programmed so that once the user finishes the survey and submits the responses, Jquery validates for a complete set of data, then captures the user's response then finally posts the data to the URL "api/friends" though an AJAX call.
### The Server
Meanwhile, the server sits still listening. It has visibility of its two routers, api & html, each desginated to their particular URL paths. The API's watch for activitivy on their URLS and are programmed to run a series of commands specific to each URL.

### The Routings
The api router waits for a post the the URL api/friends
When the AJAX call is made, posting to the api/friends URL, the apiRoutes.js takes the survey results and goes through a series of calculations to find the best match. Then pushes it to an array of objects that house survey results. 

### The Modal
Once it finds the best match the result is sent back as a response to the front-end through the AJAX call. The front-end, then takes those values and displays them to the end user through a modal.

### The API Friends List
The API friends List is a file that can be accessed from the server and displayed through a link. It is a repository of survey results in JSON format. The survey results are a mock up. Since we do not have a database to send and store survey results to, these survey reults stand as a source of candidates for the server to perform its search for the best match. It also serves as a temporary repository to store the last data set of survey results pushed in by the api router. After submitting a survey, along with the mock data your survey result will appear in your list of survey results. These results will persist for the session and disappear thereafter.



