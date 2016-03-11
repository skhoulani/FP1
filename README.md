# Final Project Assignment 1: Exploration (FP1)
DUE Friday, March 11, 2016

## My Library: graphics/turtles
My name: Samir Khoulani


To begin my project exploration, I looked into the turtle library, as it appealed to me the most. This library was pretty interesting as it involved moving the "turtle" around, which could be used to trace where it has been. The main functions learned were <i>draw, turn, erase, draw-offset</i>, and <i>home</i>. After I got these down, and experiented with shape construction shown in <b>Fig. 1</b>, I began to look into recursion.


```racket
;square with draw-offset
(draw-offset 0 100)
(draw-offset 100 0)
(draw-offset 0 -100)
(draw-offset -100 0)

;Equilateral triangle
(turn 30) 
(draw n)
(turn 120)
(draw n)
(turn 120)
(draw n)

;Square
(draw n)
(turn 90)
(draw n)
(turn 90)
(draw n)
(turn 90)
(draw n)
 ```
 <b>Figure 1.</b><i> Code for both a square and equilateral triangle.</i>


Because there was not much information I could find outlining recursion with turtles, this took a while. Seen in <b>Fig. 2</b>, my first attempt at recursing used <i>draw-offset</i> and a base case of a null list (I wasn't sure what it should be) which turned out to be completely innefective. 

```racket
(draw-offset n n)
(draw-offset (* -1 2 n) 0)
(draw-offset n (* -1 n))
(draw-offset (* 0.5 n) (* 0.5 n))
(draw-offset (* -1 n) 0)
(draw-offset (* 0.5 n) (* 0.5 n))
(draw-offset (* 0.5 n) (* 0.5 -1 n))
(draw-offset (* 0.5 -1 n) (* 0.5 -1 n))
(draw-offset n n)
(draw-offset (* -1 2 n) 0)
(draw-offset n (* -1 n))
(split (turn 0))
(recursive-call (* 0.5 n))
 ```
 <b>Figure 2.</b><i> My first attempt at creating code to be used in the recursive function.</i>

The more effective method, however, proved to involve using <i>draw</i> instead. After a significantly large portion of testing I realized that the function <i>home</i>, which just resets the turtle's position, might be perfect for a base case. Realizing that this would work, and I wouldn't get an error or and endless loop, I then took the code for the equilateral triangle I made from <b>Fig. 1</b> and started experimenting.

My first goal was to make triangles bigger and bigger from the center, but I realized that I wanted to do something with more than one triangle recursing instead. After pasting the code for my triangle three more times, I used the turn function to rotate the triangle in a way such that after each triangle was placed, the next one would be placed 90 degrees clockwise. <b>Fig. 3</b> shows the code for the four triangles that would be placed every recursive call. The result would create a Knights' Templaresque design shown in <Fig. 4</b>, with triangles recursing within eachother.

![FP1 Image Output](https://github.com/skhoulani/FP1/blob/master/FP1output.png)
<b>Figure 4.</b> <i> The resulting out put of my code.</i>


Write what you did!
Remember that this report must include:

* a narrative of what you did
* highlights of code that you wrote, with explanation
* output from your code demonstrating what it produced
* at least one diagram or figure showing your work

The narrative itself should be no longer than 350 words. Yes, you need at least one image (output, diagrams). Images must be embedded into this md file. We should not have to click a link to see it. This is github, handling files is awesome and easy!

Code should be delivered in two ways:

1. Full files should be added to your version of this repository.
1. Key excerpts of your code should be copied into this .md file, formatted to look like code, and explained.

Ask questions publicly in the email group.

## How to Prepare and Submit this assignment

1. To start, [**fork** this repository][forking]. 
  2. (This assignment is just one README.md file, so you can edit it right in github)
1. Modify the README.md file and [**commit**][ref-commit] changes to complete your report.
1. Add your racket file to the repository. 
1. Ensure your changes (report in md file, and added rkt file) are committed to your forked repository.
1. [Create a **pull request**][pull-request] on the original repository to turn in the assignment.

## Project Schedule
This is the first part of a larger project. The final project schedule is [here][schedule]

<!-- Links -->
[schedule]: https://github.com/oplS16projects/FP-Schedule
[markdown]: https://help.github.com/articles/markdown-basics/
[forking]: https://guides.github.com/activities/forking/
[ref-clone]: http://gitref.org/creating/#clone
[ref-commit]: http://gitref.org/basic/#commit
[ref-push]: http://gitref.org/remotes/#push
[pull-request]: https://help.github.com/articles/creating-a-pull-request
