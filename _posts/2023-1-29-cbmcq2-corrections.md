---
toc: true
layout: post
description: practice test corrections 
categories: [collegeboard]
title: CB MCQ 2 Corrections 
---
<html>
<head>
<style>
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

td, th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}

tr:nth-child(even) {
  background-color: #dddddd;
}
</style>
</head>
<body>

<table>
  <tr>
    <th>question #</th>
    <th>my answer</th>
    <th>correct answer</th>
    <th>corrections</th>
  </tr>
  <tr>
    <td>10</td>
    <td> A and C ( num greater than 15) and (num equals 15) and Not (num less than 15) </td>
    <td>B and C (num greater than 15) or (num equals 15) and Not (num less than 15) </td>
    <td>I now realize that num greater than 15 and num equals 15 couldn't have been the correct answer, since a number can't equal fifteen AND be greater than 15. Therefore this answer is mathematically impossible and will equal to false. The correct answer should be greater than 15 OR equal to 15.</td>
  </tr>
  <tr>
    <td>17</td>
    <td>A and B</td>
    <td> A and D</td>
    <td>because we want result to be val1 and not val2, B wouldn't be the correct answer since it would result in true for both val1 and val2. Therefore, D is the correct answer since the nested if statement means that if val1 is true, than val2 will be false. Otherwise, result will be false. </td>
  </tr>
  <tr>
    <td>21</td>
    <td>A. The number 0 is displayed.</td>
    <td>D. Nothing is displayed; the program results in an infinite loop.</td>
    <td>The program will result in an infinite loop because i will never equal 4 so the loop will go on forever. As a result, 0 won't be displayed, nothing will show up.</td>
  </tr>
  <tr>
    <td>24</td>
    <td>C. y^3</td>
    <td>B 3y </td>
    <td>the outer repeat block is executed three times, the inner repeat block is executed y times, so the block inside will be executed 3y times. y^3 wouldn't be correct because iff the value of y was 2, the inner loop would repeat two times and the outer loop would repeat three times. The statement would be executed 3 times 2, or six times. When y = 2, the value of y raised to the third power is 8, not 6. </td>
  </tr>
  <tr>
    <td>27</td>
    <td>A</td>
    <td>D</td>
    <td>A isn't the correct answer because the n<-- n+1 isn't in the correct location, it should be after all the move forward rotate left instructions, not before. </td>
  </tr>
  <tr>
    <td>28</td>
    <td>C and D</td>
    <td>A and C</td>
    <td>D is incorrect because this loop is nested inside another Repeat 2 times loop, these commands are executed again. At the end of execution, the robot will be in the same position at which it started. A is correct because With each iteration of the Repeat 4 times loop, the robot will move one square to the left and one square up and will remain facing up. After four of these iterations, the robot will finish in the gray square.</td>
  </tr>
    <tr>
    <td>30</td>
    <td>A and C</td>
    <td>B and C</td>
    <td>drawcircle function needs to be after r ←r + 1 and y ←y + 1 otherwise the values r and y will be the same. therefore a is wrong, and b is the other correct answer. </td>
  </tr>
</table>

</body>
</html>

