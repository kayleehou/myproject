---
toc: true 
layout: post
description: test corrections
categories: [markdown]
title: Tri 1 Final Corrections
comments: true

---
# Corrections
## 1
Skill 4.A:
![](https://media.discordapp.net/attachments/734598463324684389/1039294236572524674/image.png)
- my answer: The code segment displays the value of  2(5×3)  by initializing result to 2 and then multiplying result by 5 a total of three times.
- correct answer: The code segment displays the value of  2(53)  by initializing result to 2 and then multiplying result by 5 a total of three times.
- Corrections: Initializing result to 2 and multiplying it by 5 a total of three times is 2(5^3). Multiplying five by five three times, not fives times three. 

## 6
Skill 4.A:
![](https://media.discordapp.net/attachments/734598463324684389/1039294101859860491/image.png)
- my answer: prints all positive odd integers that are greater than max.
- correct answer: prints all positive odd integers that are less than or equal to max.
- corrections: plug in numbers to help make the pseudo code easier to understand. In this instance, the loop terminates when count exceeds max, so only values less than or equal to max are printed so b is the correct answer. 

## 15
Skill 1.C: 
Question: A company that develops mobile applications wants to involve users in the software development process. Which of the following best explains the benefit in having users participate?
- my answer: Users can identify and correct errors they encounter when using released versions of the software.
- correct answer: Users can provide feedback that can be used to incorporate a variety of perspectives into the software.
- corrections: My answer was a half-right, while users may be able to identify any bugs, they likely don't have the experience or skills to correct the bugs. 

## 19
Skill 1.D: 
Question: A certain programming language uses 4-bit binary sequences to represent nonnegative integers. For example, the binary sequence 0101 represents the corresponding decimal value 5. Using this programming language, a programmer attempts to add the decimal values 14 and 15 and assign the sum to the variable total. Which of the following best describes the result of this operation?
- my answer: An overflow error will occur because 4 bits is not large enough to represent either of the values 14 or 15.
- correct answer: An overflow error will occur because 4 bits is not large enough to represent 29, the sum of 14 and 15.
- corrections: The values 14 and 15 can each be represented using a 4-bit representation. However, their sum is too large to be represented with a 4-bit representation. The largest binary value that can be represented using 4 bits is 1111, which is equal to the decimal value 15. Since the sum is larger than the largest representable value, an overflow error will occur.

## 20
Skill 1.D:
Question: A video game character can face toward one of four directions: north, south, east, and west. Each direction is stored in memory as a sequence of four bits. A new version of the game is created in which the character can face toward one of eight directions, adding northwest, northeast, southwest, and southeast to the original four possibilities. Which of the following statements is true about how the eight directions must be stored in memory?
- my answer: Four bits are not enough to store the eight directions. Sixteen bits are needed for the new version of the game.
- correct answer: Four bits are enough to store the eight directions.
- corrections: Four bits can represent 2^4, or 16 pieces of information, so its not necessary for extra bits. I researched bits after this problem and now I understand. 

## 28
Skill 2.B
Question: The cost of a customer’s electricity bill is based on the number of units of electricity the customer uses. For the first 25 units of electricity, the cost is $5 per unit. For units of electricity after the first 25, the cost is $7 per unit. Which of the following code segments correctly sets the value of the variable cost to the cost, in dollars, of using numUnits units of electricity?
- my answer and correct answer: 
![](https://media.discordapp.net/attachments/734598463324684389/1039302947818967072/image.png)
- corrections: This code incorrectly charges customers who use more than 25 units of electricity. These customers are charged only for the number of units above 25. For examples, if a customer used 32 units of electricity, they should be charged $5 for the first 25 and $7 for the additional 7 units (32 – 25 = 7 units), for a total charge of $174. This code segment would incorrectly charge the customer $49 for the 32 units. Plugging in numbers would be helpful 

## 36
Skill 2.B
Question: 
![](https://media.discordapp.net/attachments/734598463324684389/1039303635831636060/image.png)
- my answer: i  ←  i + 1, APPEND(evenList, 2 * i)
- correct answer: APPEND(evenList, 2 * i), i  ←  i + 1
- corrections: my answer would skip 2, it would be the correct solution if i were initialized to 0 instead of 1. For the first iteration of the loop, twice the value of i, or 2, is appended to evenList, and then i is incremented to 2. For the second iteration of the loop, twice the value of i, or 4, is appended to the list, and then i is incremented to 3. This continues eight more times, appending the next eight even numbers to evenList.

## 39 
Skill 3.A
Question: The list wordList contains a list of 10 string values. Which of the following is a valid index for the list?
- my answer: "hello" 
- correct answer: 4
- corrections: While the list elements are strings, the indices of a list are typically nonnegative integers.

## 41
Skill 4.B
Question: 
![](https://files.slack.com/files-pri/TUDAF53UJ-F04AEDW8Q8H/image.png)
- my answer: 10
- correct answer: 20
- corrections: the last statement sets equal to p, and we know from the lines above, that p is equal to q which is 20. Therefore, r is equal to 20. 

## 46
Skill 4.B
Question: 
![](https://files.slack.com/files-pri/TUDAF53UJ-F04ARH44M24/image.png)
- my answer: The value of first is false, and the value of second is false.
- correct answer: The value of first is true, and the value of second is true.
- corrections: The third statement assigns the value of first (which is true) to second. The fourth statement assigns the value of second (which is true) to first. If second is first, and first is second, then second is false. 

## 50 
Skill 4.B
Question:
![](https://files.slack.com/files-pri/TUDAF53UJ-F04A1SP6RGS/image.png)
- my answer: initials  ←  prefix(concat(firstName, lastName), 1)
- correct answer: initials  ←  concat(prefix(firstName, 1), prefix(lastName, 1))
- corrections: This statement concatenates firstName and lastName and then assigns the first character of the result (which is the first character of firstName) to initials. Don't want to separate words, only want to take the prefix and apply 1 to each word. 

# Overall
- I learned how to read binary numbers from this article: 
<a href="https://www.lifewire.com/how-to-read-binary-4692830" rel="nofollow">Binary Link</a>

- I became more familiar with pseudo code and read this helpful Khan Academy article: 
<a href="https://www.khanacademy.org/computing/ap-computer-science-principles/ap-csp-exam-preparation/learn-ap-csp-exam-pseudocode/a/ap-csp-exam-pseudocode-reference" rel="nofollow">Khan Academy Link</a>
for example: 
a ← expression
Evaluates expression and assigns the result to the variable a.


