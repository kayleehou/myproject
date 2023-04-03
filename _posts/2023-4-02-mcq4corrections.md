---
toc: true
layout: base
description: 50 mcq
categories: [markdown]
title: MCQ 4 Collegeboard Corrections
comments: true

---
![pic](https://github.com/kayleehou/myproject/blob/master/images/mcq4score.PNG?raw=true)
# 1
Question: Which of the following best approximates the minimum possible time to execute all three processes when the two processors are run in parallel?
- My answer: 60 seconds 
- Correct answer: 80 seconds, I originally picked 60 seconds because I thought the maximum number of seconds for a process would be the minimum of all processes. However, parallel processing is only for TWO processors. Therefore, if you pair the two fastest running processors which take 30 and 50 seconds, you would get 80 seconds. 

# 49 
Question: Assume that scores contains at least two elements. Which of the following code segments will set the variable found to true if at least one student scored the maximum possible number of points on the quiz and will set found to false otherwise?
- My answer: C
- Correct answer: A, my answer was incorrect because the code segment will fail to check the last element in the list. When index is equal to the length of the list, the loop will terminate without comparing the last student score in the list to the maximum possible score. This code segment traverses the list beginning with the second element, so it is correctly comparing only student scores to the maximum possible score, which is found by accessing scores[1]. The variable found will only be set to true when a student’s score equals the maximum possible score. The code also sets the number of iterations to LENGTH(scores) - 1 to reflect that the first list element (maximum score) is skipped.

# 50 
Question: Suppose a large group of people in a room were all born in the same year. Consider the following three algorithms, which are each intended to identify the people in the room who have the earliest birthday based on just the month and day. For example, a person born on February 10 is considered to have an earlier birthday than a person born on March 5. Which of the three algorithms will identify the correct people?
- My answer: II and III only 
- Correct answer: II only, Algorithm III does not work correctly. Algorithm III chooses the person(s) with the earliest day, disregarding the month. For example, algorithm III will incorrectly determine that a person born on February 1 has an earlier birthday than a person born on January 5. I misinterpreted the question as saying the first day of the year. 

# Additional Searches
- heuristic: When an algorithm uses a heuristic, it no longer needs to exhaustively search every possible solution, so it can find approximate solutions more quickly. A heuristic is a shortcut that sacrifices accuracy and completeness. [khan academy link](https://www.khanacademy.org/computing/ap-computer-science-principles/algorithms-101/solving-hard-problems/a/using-heuristics)
