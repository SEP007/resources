# Time behavior of Patat

## Measurement collection

The Response-Time metric is used to measure the time-behavior of Patat. With the help of Mozilla Firebug, it is measured how long it takes before Patat responds to a user operation, meaning that the page is fully loaded.  Measurements are conducted during functional tests of user stories to avoid duplicate testing. Developer stories are not taken into account because they either do not have any direct impact on user operations or affect too many user operations at once. The response time of each operation that is affected by a user story is measured. Along with the response time and the name of the operation, the input to and the output of the operation is documented.  If an operation has been tested before, the same or similar input data should be used to be able to compare the response times. If the response time of at least one of the operations, which are affected by the user story, is more than 5 seconds, the user story will not be accepted but reassigned.  
The team will be informed immediately or latest at the next sprint planning meeting, if the  response time of an operation, which has been tested before, increases by at least 1.5 second, although the input to and output of the operation were the same or similar. Causes for the increase in response time have to be  identified within the team, then counter-measures have to be taken accordingly. 

## Measurement results

| User story | Input                     | Action                           | Output                      | Measured time
| :--------: | :-----------------------: | -------------------------------: | --------------------------: | --------------:
| #6         | Restaurant: Franks Imbiss | Click on map in restaurant view	| Directions for walking mode |	5,22
|			 | 							 | Select driving mode in map view  | Directions for driving mode |	7,27
| #7         | Customer data: dani, dani,| Create new customer user account | Log in view    			  | 1,78
|            | Daniela Holzner,          |									|							  |
|			 | danyholzner@freenet.de	 | 									|							  |
| #14        | User: tdeekens, 123       | Sign in & go to menu view        | Click on edit in menu view  | 1,59
|            |                           | Change category and save         | Menu view                   | 1,74

Both measurements conducted for user story #6 exceed 5s. The team will be informed about this during the next meeting.