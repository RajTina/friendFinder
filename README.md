# friendFinder App
### Overview

In this activity, building a compatibility-based "FriendFinder" application. This full-stack site will take in results from  users' surveys, then compare their answers with those from other users. The app will then display the name and picture of the user with the best overall match.

## Heroku live link:
https://vast-garden-62466.herokuapp.com/

##Technologies Used

-JavaScript
-jQuery
-node.js
-Express.js
-HTML
-Bootstrap

### Instructions

1.  Survey has 10 questions of our choosing. Each answer is on a scale of 1 to 5 based on how much the user agrees or disagrees with a question.

2.  `server.js` file  require the basic npm packages : `express` and `path`. Our server.js file sets up the Express server, specifying      our port number, the npm packages that need to be loaded, and also the routes, which we have externalized

3.  `htmlRoutes.js` file should include two routes: There are 2 separate HTML files (home.html and survey.html) that serve as the front-end portion of our code; they determine what the user sees (the homepage and the survey, which will also show the resulting best match) 

   * A GET Route to `/survey` which should display the survey page.

4. `apiRoutes.js` file  contain two routes:

   * A GET route with the url `/api/friends`. This will be used to display a JSON of all possible friends.
   * A POST routes `/api/friends`. This will be handle incoming survey results. This route will also be used to handle the compatibility logic.

    Our 2 routing files (htmlRoutes.js and apiRoutes.js) determine the back-end logic (based on the request being made, the response that gets sent to the browser); the HTML routes display the survey and the homepage based on the URL that is accessed, and the API routes send back existing content in our server-side data or add new friends
   * A default, catch-all route that leads to `home.html` which displays the home page

5.   Application's data being saved inside of `app/data/friends.js` as an array of objects.

6. Determine the user's most compatible friend using the following as a guide:

   * Convert each user's results into a simple array of numbers (ex: `[5, 1, 4, 4, 5, 1, 2, 5, 4, 1]`).
   * With that done, compare the difference between current user's scores against those from other users, question by question. Add up the differences to calculate the `totalDifference`.
     * Example:
       * User 1: `[5, 1, 4, 4, 5, 1, 2, 5, 4, 1]`
       * User 2: `[3, 2, 6, 4, 5, 1, 2, 5, 4, 1]`
       * Total Difference: **2 + 1 + 2 =** **_5_**
   * Used the absolute value of the differences.  no negative solutions! App calculated both `5-3` and `3-5` as `2`, and so on.
   * The closest match will be the user with the least amount of difference.

7. Once you've found the current user's most compatible friend, display the result as a modal pop-up.
   * The modal should display both the name and picture of the closest match.
   
   ###Built With

Visual Studio Code - Text Editor
Terminal/Gitbash

##Author

Tina Azad
