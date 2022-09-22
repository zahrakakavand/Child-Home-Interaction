isher’s Exact Test is a statistical test that is used to analyze contingency tables.
This non-parametric test is utilized to show dependency of parameters on a small sample.
In this project, we used Fisher's Exact test to investigates the dependency of level of abstraction and gamification to task completion rate.
For this purpose, we categorized different task completion rates into 4 categories (following table):


|**Rate Categories**|Rate 1|Rate 2|Rate 3|Rate 4|
| ------------- | ------------- | ------------- | ------------- |------------- |
|**Number of Failed Tasks**| 0 or 1 or 2 |3 or 4 or 5|6 or 7 or 8| more than 8|

First, we need to load the rate data and change their values to the categorical values using the following python code:

```
# 0-1-2, 3-4-5, 6-7-8, more
Rcategory = []
for i in range(len(Rate)):
    rcat = 16 - Rate[i]
    if rcat == 0 or rcat == 1 or rcat == 2:
        Rcategory.append(0)
    elif rcat == 3 or rcat == 4 or rcat == 5:
        Rcategory.append(1)
    elif rcat == 6 or rcat == 6 or rcat == 6:
        Rcategory.append(2)
    else:
        Rcategory.append(3)
```

To calculate the count of users in each rate category we used the following piece of python code:

```
G1Rcat = [0,0,0,0]
for i in range(8):
    G1Rcat[Rcategory[i]] += 1
print('G1Rcat', G1Rcat)

G2Rcat = [0,0,0,0]
for i in range(8):
    G2Rcat[Rcategory[i+8]] += 1
print('G2Rcat', G2Rcat)

G3Rcat = [0,0,0,0]
for i in range(8):
    G3Rcat[Rcategory[i+16]] += 1
print('G3Rcat', G3Rcat)

G4Rcat = [0,0,0,0]
for i in range(8):
    G4Rcat[Rcategory[i+24]] += 1
print('G4Rcat', G4Rcat)
```
The result of the above code is as follows:
```
G1Rcat [6, 2, 0, 0]
G2Rcat [3, 5, 0, 0]
G3Rcat [1, 3, 1, 3]
G4Rcat [1, 2, 0, 5]
```

As mentioned in the paper, the specified groups of users are as follows:

|     |**Level of Abstraction: 3D**|**Level of Abstraction: text**|
| ------------- | ------------- | ------------- |
|**Game-based**| G1: 3D game-based design |G2: Verbal game-based design|
|**Non-game**| G3: 3D non-game design |G4: Verbal non-game design|

In this research, Two experiment was conducted:
1) to determine if there was a significant association between Level of Abstraction and Task Completion rate.
2) to determine if there was a significant association between Gamification and Task Completion rate.

For each of the above two experiments we have to use 2 Fisher's exact test. For investigating the association between level of abstraction and task completion rate we do the Fisher's exact test between group 1 and group 2 which have the same gamification approach but different level of abstractions. Then, do another Fisher's exact test between group 3 and group 4 as well. The results are available in the following table
|   |**G1 (3D)**|**G2 (Verbal)**| **Total**|
| ------------- | ------------- |------------- |------------- |
| Rate 1 | 6 |3|9|
| Rate 2 | 2 |5|7|
| Rate 3 | 0 |0|0|
| Rate 4 | 0 |0|0|
| Total  | 8 |8|8|


|   |**G3 (3D)**|**G4 (Verbal)**| **Total**|
| ------------- | ------------- |------------- |------------- |
| Rate 1 | 1 |1|2|
| Rate 2 | 3 |2|5|
| Rate 3 | 1 |0|1|
| Rate 4 | 3 |5|8|
| Total  | 8 |8|16|

