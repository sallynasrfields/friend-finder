# friend-finder
An express based website used to help people find friends with similar interests.

## How it works.

To use this website, the user must first fill out a survey of 10 questions. Once all of the questions are answered, the user must submit the survey. Results are sent to back-end server and are compared with the results of all other submissions. A best match is calculated, then returned back to the user in the form of a "Pop-up" message. For more information - user can also view survey results of all previous submission by navigating to the link "API Friends List" at the bottom of the survey page.


## How it was built.

This is an example of a full stack application that uses AJAX, Express and JSON to post data to server, process the data and display results back to the end user. The main components of this application is 1) a server (server.js) 2) two javascript files for routings (apiRoutings & htmlRoutings) 3) a javascript file to house the survey results in JSON (friends.js) 4) and two HTML files (home.html & survey.html).

The end-user graphical interface was created through the usage of html & bootstrap. To start with the user is introduced to the application through the home page. A button is placed on the home page that nagivates the user to the survey.

Logic on this page was programmed so that once the user finishes the survey and submits the responses, Jquery validates for a complete set of data, then captures the user's response then finally posts the data to the server though an AJAX call.

When the server receives the data, it then takes the survey results and goes through a series of calculations to find the best match. Once it finds the best match the result is sent back to the front end, where a modal pops up displaying the name and picture of the best match.

