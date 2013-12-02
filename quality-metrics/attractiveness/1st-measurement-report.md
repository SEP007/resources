# Attractiveness of the Patat

## Measurement collection

To obtain a quantifiable value for the level of attractiveness of the Patat three interviews with users were conducted. The users were asked to browse [Patat's website](http://sep007.tdeekens.name/) to familiarize themselves with it and then fill in the [survey](https://www.surveymonkey.com/s/GKFNJ5G). The survey addressed issues relates to the use of colors, graphics, alignment of items etc.

The main goal of the survey is to obtain a numeric value designating the level of attractiveness of the Patat. For this purpose, the survey is structured in a way that allows to transform user's ratings of statements about Patat's interface into numbers. Every statement in the survey can get a score from 1 to 5, 5 designating the highest level of attractiveness for a given aspect. For example, when user strongly disagrees with a statement, this statement gets a score 1. If the user strongly agrees with a statement, it gets a score of 5.
A sum of ratings for every statement is then calculated. A total number of 25 statements results in the highest possible value per one questionnaire being 25 x 5 = 125. To get the attractiveness value a sum is divided by the total maximum value (which, in the given case is 125).
The closer the obtained value is to 1, the more attractive Patat is to its users.

## The first measurement results

The following table contains the results obtained from the above mentioned interviews. The column "Sum" designated a total number of points per questionnaire, whereas "Result" designates the value of Attractive Interaction metric calculated as a relation of Sum to maximum possible points (125).

| Respondent        | Sum           | Result |
| :---------------: | :-------------: | -----: |
| 1                 | 120             | 0.96   |
| 2                 | 84              | 0.67  |
| 3                 | 100             | 0.80   |

As can be seen, the results vary quite significantly but not drastically. The differences can be attributed to the backgrounds of users: while respondent #1 has no technical background, respondent #2 has academic knowledge about the issues addressed in the survey and respondent #3 professionally works with software. Thus, obtained values were treated slightly differently when discussed within the team. The average result value of 0.81 was considered satisfactory, however a goal was set to obtain values higher than 0.80 for individual evaluations in the next measurement.

### Qualitative data

To improve Patat's attractiveness, every user was asked for feedback about the aspects of the interface which they found not appealing. The discovered issues are subject for discussion within the development team and can possibly be taken into consideration when implementing future user stories.

#### Main problem areas

##### Color scheme
Two respondents pointed out the relative monotony of the color scheme used in Patat. Insufficient use of contrasting colors hinders user's concentration on certain aspects of the page and makes Patat seem white and empty.

##### Home page
![alt text](https://raw.github.com/SEP007/resources/master/quality-metrics/attractiveness/resources/home-page.png "Patat's home page")
Related to the problem above, layout and color of items in the navigation bar was described as unsatisfactory by one of the respondents. They expressed concern of not being able to locate themselves with respect to the items in the bar due to lack of indication of current position by means of different colors or shapes. This issue is not explicitly in the score of the discussed survey, but it was considered as a valuable feedback regarding Patat's usability.

##### Search results page
![alt text](https://raw.github.com/SEP007/resources/master/quality-metrics/attractiveness/resources/search-results.png "Patat's search results page")
Items of the pagination bar were regarded as small by one of the respondents and it was also pointed out that the functionality behind them (namely, the possibility to navigate to a certain item in the list) is not apparent (the latter is out of score of the measurement at hand, however it was treated as a feedback for Patat's usability). 
Separators were also described as being of not sufficient size by one of the respondents, as well as the size and positioning of its content.
Two of the respondents addressed the positioning and font of calculated price and distance as being inadequate.

## The second measurement results

The second measurement was conducted in a different fashion due to low level of Patat's interface changes at the time of the collection. The respondents were asked [to rate Patat's attractiveness](https://docs.google.com/forms/d/1ZFX-bCfskDZz6wb73jjNXzwU1ydGZz7Qg8PEa9dCZKg/viewform) on a scale from 1 to 10 after being shown a short demo of the system and using it if needed.

| Respondent        | Rating          |
| :---------------: | :-------------: |
| 1                 | 8               |
| 2                 | 7               |
| 3                 | 10              |
| 4                 | 10              |
| 5                 | 10              |
| 6                 | 10              |
| 7                 | 7               |
| 8                 | 7               |
| 9                 | 7               |
| 10                | 8               |
| 11                | 8               |

An average value of 0.84 was considered satisfactory as it is above the lowest acceptable border of 0.80.

### Qualitative data

The second measurement collection helped to identify the issues with Patat's interface that were not considered after the first measurement. These included inconsistencies in use of colors, not sufficient interactiveness of certain elements and unexpected, non-intuitive behaviour of the location page.

## The third measurement results

The third measurement was performed after the last sprint, when all accepted user stories were integrated into a final version of the system. During the project Patat's interface went through substantial changes as several new elements were introduced. The changes did not only occur in the originally existing views of Patat: a new view was created for displaying the favorites of a customer. Hence, the original questionnaire [was modified](https://docs.google.com/forms/d/1sqzUdpvnK8l1CAtPz0Tzyq-VAfmzOckCoJIiBFrvtL8/viewform) to take into account these changes and obtain the attractiveness value for the complete system. This resulted in a different maximum possible score of 165 per questionnaire.

| Respondent        | Sum           | Result |
| :---------------: | :-------------: | -----: |
| 1                 | 148             | 0.90   |
| 2                 | xxx             | x  |
| 3                 | xxx             | x   |

### Qualitative data

According to the respondents, the areas of Patat's interface design that could be mproved in the future included:
  - readability of the elements (potentially caused by the choice of color scheme or fonts)
  - not intuitive functionality behind the items in the pagination bar of the dishes view
  - size of the map preview in the restaurant page
  - non-compliance of the "hot deal" sign with the style of the other elements

Nevertheless, the results of the measurement were considered acceptable, as the final value exceeded the lowest theshold. The respondents were satisfied with the appearance of Patat and emphasized on ease of navigation and ...
 - 