# Hi there 
Im Frankie

Whats you favorite animal?

# About me
I learned java in 10th grade

I took 3 coding classes in highschool

My greatest piece of work is a rubik's cube solving robot

it took 21 months and 9 versions

I unfortunately do not have a github history for the code. It was all made in eclipse IDE

lots of code was written on paper/notes app vis stylus pen - its the way I was first taught in 10th grade

# About my project

This project began as just a coding challenge to see what I could do. I began this project at a time when I was quite a weak programmer, and there is a very clear improvement in my code as you inspect newer versions. Because I never intended to submit this as a portfolio, I do not have documentation of every piece of code I have ever made. My first teacher frequently told the class that in the industry, most code is made on paper before being put into the computer. As a result, I have lost some of my work brainstorming algorithms.

I think the coolest thing about the entire process is that you can see my skills improve between different versions. Despite java being a object-oriented language, I think what is most notable is using methods(functions) more effectively. Old versions had the algorithm hardcoded into the main method. I've come quite a long way.

I've attached some of the more notable versions of code as text files. All my code was tested and debugged on eclipse IDE. My apologies if this is not what was intended for a project link, I've never used GitHub before.

One important thing. Rubik's cube notation represents a specific permutation of the cube by describing the face and direction that was altered in a specific order. The moves go as followed: U = up face(top), F= front face, R = right face, L = left face, D = down face(bottom), B = back face. Usually white is the top face and green is the front face. Seeing the letter alone means a clockwise rotation while a apostrophe following the letter represents a counterclockwise turn. the number 2 after the letter represents turning the face twice(180 degrees). For example, the scramble UB'L2 means turning the top face 90 degrees clockwise, then the back face counterclockwise, then the left face 180 degrees. note that turning a face clockwise and counterclockwise 180 degrees yields the same permutation.

# v4 
The v4 version of code represents the cube as a 54 character string, where each char is a square on a set side. Looking at a face of the cube, the order of the 9 chars that represent the face go from left to right, then top to bottom. I would consider this code my first "breakthrough" as my first solid attempt as using a algorithm called Breadth first search. This algorithm makes a tree of the cube by exploring every possible move, saving it, then exploring every possible move within the new saved nodes. Take a random scramble, and apply all the moves possible one at a time, and save their position along with their move order in a HashMap. you now have 18 nodes, and a depth of 1 move away from your starting scramble(U,R,L,F,B,D,U',R', etc...). You then repeat the process by exploring all possible moves with the new 18 nodes. This code fails because of its excess use of memory. notice that for every position, exploring 1 more move means that for every existing node on the bottom of the tree, 18 more will be added for a depth increase of 1. This forces us to save 18^n position for a depth of n. We also know that ALL permutations can be solved in 20 moves or less, meaning worse case scenario we are saving 18^20 positions. You can reduce this to 2*18^10 by creating a second tree where the starting node is the solved position of the cube, and combining the 2 HashMap keys(move order) when both trees have a identical string. You can also recycle old nodes because the key of the HashMap is already the saved move order. Because each string representing the cube is 54 characters long, you are using 108 bytes per node, meaning you need 108 * 2 * 18^10 bytes of RAM to succeed 100 percent of the time. This specific version of code attempted to tackle this problem by taking a random mode a depth 6-7 moves from the starting node to use to start a new tree. Unfortunately getting 2 trees to have 2 identical strings twice proved to be quite a challenge. 

# v9



