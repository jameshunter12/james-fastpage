---
toc: true
layout: post
description: grading the example preformance tasks (4)
categories: [markdown, java]
title: PT.2 Preformance Task Blog
---

# Submission 1
<html>
<style>
    table, th, td { 
        border:2px solid white;
    }
<!DOCTYPE html>
<html>
<head>
   <style>
      table, th, td {
         border: 1px solid green;
      }
   </style>
<body>
   <table>
         <th>Reporting Category</th>
         <th>Student Score</th>
         <th>College Board Score</th>
         <th>Comments</th>
      </tr>
      <tr>
         <td>Program Purpose and Function</td>
         <td>0</td>
         <td>0</td>
         <td>The purpose of the program is stated as "for you to see all the animals and to identify them when you're asked later" but it does not state the problem being solved or creative interest being pursued. The response also does not accurately describe the functionality demonstrated in the video and confuses input and output.</td>
      </tr>
      <tr>
         <td>Data Abstraction</td>
         <td>0</td>
         <td>0</td>
         <td>Two code segments are provided, one showing storage of data in a list named animalImages, and the other showing another list named animalList. However, animalList is not used in either code segment. The response describes the data contained in animalList, but it also describes the images from animalImages, which are stated to be in the list.</td>
      </tr>
      <tr>
         <td>Managing Complexity</td>
         <td>0</td>
         <td>0</td>
         <td>The response does not include a program code segment that uses a list to manage complexity. Both code segments show data being stored in a list, but neither contain code using a list. The code is not complex. The response also does not explain how the list manages complexity, it just states that the array allows you to store more than one variable making it shorter and more complex, but it does not explain how it would be written differently without the list.</td>
      <tr>
      </tr>
         <td>Procedural Abstraction</td>
         <td>0</td>
         <td>0</td>
         <td>The response includes a student-developed procedure called evaluateGuess with one explicit parameter, guess, and a call to this procedure in a second code segment using the argument guess. The response describes the functionality of the procedure as determining if the user's guess is right or wrong. However, the response does not describe how this procedure contributes to the overall functionality of the program.</td>
      </tr>
      <tr>
         <td>Algorithm Implementation</td>
         <td>0</td>
         <td>0</td>
         <td>The student-developed algorithm within the procedure, evaluateGuess, includes sequencing, iteration (a for loop) and selection (an if statement). The response provides a minimal description of the algorithm, but it does not provide enough detail for someone to recreate it.</td>
      </tr>
      <tr>
         <td>Testing</td>
         <td>1</td>
         <td>1</td>
         <td>The first call is for "dog" which is a correct guess. The second call is for "mouse" which is an incorrect guess. The response also describes the conditions being tested in the procedure, which are whether the guess is equal to one of the animals in animalList or not. The response also states the different results of the two calls, the first call results in "You got a point!" and the second call results in "That's 1 strike."</td>
      </tr>
   </table>
</body>
</html>

# Submission 2
<html>
<style>
    table, th, td { 
        border:2px solid white;
    }
<!DOCTYPE html>
<html>
<head>
   <style>
      table, th, td {
         border: 1px solid green;
      }
   </style>
<body>
   <table>
         <th>Reporting Category</th>
         <th>Student Score</th>
         <th>College Board Score</th>
         <th>Comments</th>
      </tr>
      <tr>
         <td>Program Purpose and Function</td>
         <td>1</td>
         <td>1</td>
         <td>The purpose of the program is specified as to explore the user's creativity through the expression of poetry using their words. The response also describes the functionality, showing the poems according to the user's inputs of words and setting of articles, resulting in multiple different poems with different word orders and another generation of poems with different words and no articles. The response also describes the input and output of the program.</td>
      </tr>
      <tr>
         <td>Data Abstraction</td>
         <td>1</td>
         <td>1</td>
         <td>Two code segments are provided, the first shows data being stored in a list named nounList and the second shows the data being accessed from the list under a new name, wordList, since it is passed as a parameter. The response identifies what is stored in the list, stating that the data contains nouns that must be in certain specific locations within the poem to make logical sense.</td>
      </tr>
      <tr>
         <td>Managing Complexity</td>
         <td>1</td>
         <td>1</td>
         <td>The response includes code that uses lists of words to manage complexity when generating poetry. It mentions that without the list, the noun inputs would have to be stored in different variables and would have to be invoked separately. Another method would have to be used to randomize selection such as generating a random integer, which would require writing individual statements for each possible int generated and making the code more cluttered.</td>
      <tr>
      </tr>
         <td>Procedural Abstraction</td>
         <td>1</td>
         <td>1</td>
         <td>The response includes a student-developed procedure called createPoems, with four parameters that are used in the procedure. The response also describes how the procedure contributes to the overall program by stating that it is used in conjunction with the user inputs and builds poems according to how many poems the user specified and whether the user wanted articles in the poems.</td>
      </tr>
      <tr>
         <td>Algorithm Implementation</td>
         <td>1</td>
         <td>1</td>
         <td>The student-developed algorithm within the procedure, createPoems, includes sequencing, selection (if statement), and iteration (while loop). The response explains in detail how the algorithm works, it sequentially first defines a variable to count the number of poems generated and defines an empty string, then it has iteration that generates as many poems as the user specified by running through the selection statements which call articlePoem or noArticlePoem each time.</td>
      </tr>
        <tr>
         <td>Testing</td>
         <td>1</td>
         <td>1</td>
         <td>The response describes two calls to a specific procedure, createPoems, that result in different code being executed by varying the argument for the last parameter. The first call is createPoems(nounList, verbList, adverbList, 1) and the second call is createPoems(nounList, verbList, adverbList, 0). The last parameter represents the article preference setting. The response describes the conditions being tested by the code, which are whether the user input is 1 or 0 for the article preference setting.</td>
      </tr>
   </table>
</body>
</html>

# Submission 3
<html>
<style>
    table, th, td { 
        border:2px solid white;
    }
<!DOCTYPE html>
<html>
<head>
   <style>
      table, th, td {
         border: 1px solid green;
      }
   </style>
<body>
   <table>
         <th>Reporting Category</th>
         <th>Student Score</th>
         <th>College Board Score</th>
         <th>Comments</th>
      </tr>
      <tr>
         <td>Program Purpose and Function</td>
         <td>1</td>
         <td>0</td>
         <td>The video demonstrates a program that allows the user to select two Marvel characters from a drop-down menu, displaying their rankings and the winner of the battle using an image. The response describes the program's function, functionality demonstrated in the video, input and output. The response describes the input as the different button clicks to change the screens and the character names selected from each drop-down box.</td>
      </tr>
      <tr>
         <td>Data Abstraction</td>
         <td>1</td>
         <td>1</td>
         <td>Two code segments are provided, the first showing data being stored in a list named firstCharacterList and the second accessing the data from that list in a loop. The response identifies the data stored in the list as the power rankings and URL for the image of a character selected from a drop-down box.</td>
      </tr>
      <tr>
         <td>Managing Complexity</td>
         <td>1</td>
         <td>1</td>
         <td>The response includes a list that combines six rankings and an image URL for a character into one collection, managing complexity in the program code. The response explains that the list condenses the code, and without it the program would need more parameters and more steps to find the winner.</td>
      <tr>
      </tr>
         <td>Procedural Abstraction</td>
         <td>1</td>
         <td>1</td>
         <td>The response describes a procedure called findWinner that compares the average power rankings of two Marvel characters passed as parameters. The procedure changes the winner screen to display the character with the higher average and if the averages are the same, it displays a "tie" image. The procedure contributes to the overall program by determining the hypothetical winner in a battle between characters.</td>
      </tr>
      <tr>
         <td>Algorithm Implementation</td>
         <td>1</td>
         <td>1</td>
         <td>The student-developed algorithm in the findWinner procedure uses sequencing, selection, and iteration to compare the average power rankings of two characters selected from a drop-down menu. The algorithm iterates through the list of each character, sums up the rankings, and divides by 6 to get the average. It then compares the averages using a conditional statement to determine the winner and display their name and image on the winner screen.</td>
      </tr>
        <tr>
         <td>Testing</td>
         <td>1</td>
         <td>1</td>
         <td>The response describes two calls to a procedure, findWinner, with different arguments (Vision and Bishop; Carnage and Venom) that lead to different results. The response explains how the procedure uses an if-else statement to determine the winner based on average ranking and displays the winner's image and name or a tie image.</td>
      </tr>
   </table>
</body>
</html>

# Submission 4
<html>
<style>
    table, th, td { 
        border:2px solid white;
    }
<!DOCTYPE html>
<html>
<head>
   <style>
      table, th, td {
         border: 1px solid green;
      }
   </style>
<body>
   <table>
         <th>Reporting Category</th>
         <th>Student Score</th>
         <th>College Board Score</th>
         <th>Comments</th>
      </tr>
      <tr>
         <td>Program Purpose and Function</td>
         <td>1</td>
         <td>1</td>
         <td>The video demonstrates a program that tests critical thinking skills by collecting input through a text entry field for guessing an 8-letter word, and displays the matching letters. The user inputs words, correctly guessing "touching" in 4 tries, but failing to guess "sandwich" in 6 tries. The input is a word the user inputs, and the output is the color scheme of the corresponding letters.</td>
      </tr>
      <tr>
         <td>Data Abstraction</td>
         <td>0</td>
         <td>0</td>
         <td>Two code segments are provided, the first shows data being stored in a list named 'guesses' but in the second segment, data stored in the list is not being used, only the length of the list is accessed. The response states that the data in the list represents all the user's word inputs.</td>
      </tr>
      <tr>
         <td>Managing Complexity</td>
         <td>1</td>
         <td>0</td>
         <td>The response describes a program code segment that uses a list named "guesses" to keep track of the user's guesses, but the list is not used to manage complexity and can be replaced with a single counter variable. The response does not explain how the list manages complexity and instead mentions that the list's purpose is to stop the game after 6 guesses.</td>
      <tr>
      </tr>
         <td>Procedural Abstraction</td>
         <td>1</td>
         <td>1</td>
         <td>The response includes a student-developed procedure, isitcorrect, which compares a user input guess to the correct word or letter positions. The procedure is called in the program with the argument answer. The procedure checks the user's answer every time they input a guess and contributes to the overall program.</td>
      </tr>
      <tr>
         <td>Algorithm Implementation</td>
         <td>1</td>
         <td>1</td>
         <td>The response describes a student-developed algorithm called isitcorrect that includes sequencing, selection, and iteration. The algorithm checks if a user's input is 8 letters, if so it checks for position and accuracy of each letter, turning the output letters green, yellow or red accordingly, it also determines when the 'You Win' or 'You Lose' screen will show up based on the input.</td>
      </tr>
        <tr>
         <td>Testing</td>
         <td>0</td>
         <td>0</td>
         <td>The response describes the conditions being tested in a procedure, specifically "whether or not the user inputs the right letter in the right position" and "whether or not the user inputs the right letter in the wrong position." It also describes the result of these conditions, with the letter color changing to green or yellow respectively. The response does not provide specific arguments used in the procedure call.</td>
      </tr>
   </table>
</body>
</html>