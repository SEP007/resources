# Time behavior of Patat

## Measurement collection

The Response-Time metric is used to measure the time-behavior of Patat. With the help of Mozilla Firebug, it is measured how long it takes before Patat responds to a user operation, meaning that the page is fully loaded.  Measurements are conducted during functional tests of user stories to avoid duplicate testing. Developer stories are not taken into account because they either do not have any direct impact on user operations or affect too many user operations at once. The response time of each operation that is affected by a user story is measured. Along with the response time and the name of the operation, the input to and the output of the operation is documented.  If an operation has been tested before, the same or similar input data should be used to be able to compare the response times. If the response time of at least one of the operations, which are affected by the user story, is more than 5 seconds, the user story will not be accepted but reassigned.  
The team will be informed immediately or latest at the next sprint planning meeting, if the  response time of an operation, which has been tested before, increases by at least 1.5 second, although the input to and output of the operation were the same or similar. Causes for the increase in response time have to be  identified within the team, then counter-measures have to be taken accordingly. 
To be able to compare measured times with one another, measurements are always conducted at the same machine and on the live server.

## Measurement results

### 1st measurement

| User story | Input                     				  | Action                           | Output                      | Measured time
| :--------: | :----------------------------------------: | -------------------------------: | --------------------------: | --------------:
| #6         | Restaurant: Franks Imbiss 				  | Click on map in restaurant view	 | Directions for walking mode |	5,22
| #6		 | 							 				  | Select driving mode in map view  | Directions for driving mode |	7,27
| #7         | Customer data: dani, dani, Daniela Holzner,| Create new customer user account | Log in view    			   | 1,78
| #14        | User: tdeekens, 123       				  | Sign in & go to menu view        | Click on edit in menu view  | 1,59
| #14        |                           				  | Change category and save         | Menu view                   | 1,74

Both measurements conducted for user story #6 exceed 5s. The team was informed about this. Within the team, it was agreed upon that no action will be taken because the negative time behavior is caused by a plugin that is out of our control.

### 2nd measurement

| User story | Input                     				  | Action                           | Output                      | Measured time
| :--------: | :----------------------------------------: | -------------------------------: | --------------------------: | --------------:
| #13        | Customer: nils, nils, Nils Holgersson1 | Create new customer user account	 | Log in view & email |	2,77
| #13   		 | | Signup has not been completed; logging in is tried anyways  | Customer is not logged in |	2,34
| #13        | | Complete sign up by clicking on link in email | Completed signup view | 1,87
| #13        | | Log in | Click on edit in menu view  | 2,2
| #13        | Restaurant: karlsson, karlsson, Karlsson, Karlssons Garage, Linnegatan 54, 41308 Göteborg | Create new restaurant account |  Log in view | BUG
| #13        | | Complete sign up by clicking on link in email | Completed signup view | 1,79
| #13        | | Sign in | Menu view | 2,01
| #22        | Restaurant: Karlssons Garage | Click on add new dish | Edit view | 2,13
| #22        | Dish: Advertised, Köttbullar, Pasta, 5€, Very delicious köttbullar with potatoes | Add new advertised dish | Menu view | 2,04
| #22        | | Click on edit dish | Edit view | 2,01

All conducted measurements, except from one where a bug has been found, resulted in a time below 5s. For the identified bug, a issue has been created in GitHub. All other tested user stories are accepted from the time behavior point of view. One lessons learned is that the measurements have to be conducted at the same location in order to be able to compare measurements. 

### 3rd measurements

| User story | Input                     				  | Action                           | Output                      | Measured time
| :--------: | :----------------------------------------: | -------------------------------: | --------------------------: | --------------:
| #56, 57    | User: kostas, 123 | Log in, Search for dishes around current location	 | Dishes view |	4,7
| #56, 57  	 | | Favorite one not yet favorited dish | Dish view |	0,44
| #56, 57    | | Unfavorite the recently favorited dish | Dish view | 0,33
| #56, 57    | | Go to my favorites | Favorites view  | 2,14
| #56, 57    | | Go to tab places | Favorites view | 2,21 
| #56, 57    | | Navigate to restaurant page by clicking on a restaurant name | Imbiss view | 6,92
| #4, 51     | | Search for dishes around current location, navigate to restaurant page by clicking on a restaurant name | Restaurant view | 6,04
| #4, 51     | User: kostas, 123 | Log in, search for dishes and navigate to same restaurant as previously | Restaurant view | 6,23
| #4, 51     | | Toggle comments | Restaurant view | 0
| #4, 51     | | Leave comment for restaurant | Restaurant view | 5,62
| #9, 25     | | Go to sign up | Sign up view | 2,48
| #9, 25     | | Click on Sweden flag | Sign up view | 2,51

All measurements, except from measurements taken at the imbiss view resulted in positive results. Loading the imbiss view takes more than 5s because it has been evolved with a lot of new features: translation, viewing and leaving comments, favoriting, displaying the category, ... It has to be discussed within the team whether counter-measurements can/will be taken.
