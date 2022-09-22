isher’s Exact Test is a statistical test that is used to analyze contingency tables.
This non-parametric test is utilized to show dependency of parameters on a small sample.
In this project, we used Fisher's Exact test to investigates the dependency of level of abstraction and gamification to task completion rate.
For this purpose, we categorized different task completion rates into 4 categories (following table):


|**Rate Categories**|Rate 1|Rate 2|Rate 3|Rate 4|
| ------------- | ------------- | ------------- | ------------- |------------- |
|**Number of Failed Tasks**| 0 or 1 or 2 |3 or 4 or 5|6 or 7 or 8| more than 8|

And specified the groups of users as follows:

|     |**Level of Abstraction: 3D**|**Level of Abstraction: text**|
| ------------- | ------------- | ------------- |
|**Game-based**| G1: 3D game-based design |G2: Verbal game-based design|
|**Non-game**| G3: 3D non-game design |G4: Verbal non-game design|

In this research, Two experiment was conducted:
1) to determine if there was a significant association between Level of Abstraction and Task Completion rate.
2) to determine if there was a significant association between Gamification and Task Completion rate.

For each of the above two experiments we have to use 2 Fisher's exact test. For investigating the association between level of abstraction and task completion rate we do the Fisher's exact test between group 1 and group 2 which have the same gamification approach but different level of abstractions. Then, do another Fisher's exact test between group 3 and group 4 as well. The results are available in the following table
|   |**G1 (3D) **|**G2 (Verbal)**| **Total**|
| ------------- | ------------- |------------- |------------- |
| Rate 1 | 6 |3|9|
| Rate 2 | 2 |5|7|
| Rate 3 | 0 |0|0|
| Rate 4 | 0 |0|0|
| Total  | 8 |8|8|
