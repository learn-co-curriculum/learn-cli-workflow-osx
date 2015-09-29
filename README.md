# Using the Learn CLI

## What is the Learn CLI?

The Learn CLI is a command line interface (aka application) that makes it easy for you interact with Learn from your Terminal. You can think of it as a handful of shortcut commands that make it easy for you to get your work done. 

In this lesson, we'll walk through the steps you need to take to solve a lab on Learn, with a little help from the Learn CLI.

## Opening a Lesson

To start working on a lab on Learn, you need get it opened up on your computer. There are a couple different ways to do this:

1. The first, and simplest, is to just click the `Open` button in the toolbar at the top of a lab on Learn—don't try to do this just yet, you'll do this in the next lesson. When you click Open, you'll notice a Terminal window briefly pop up, then your text editor will open with the contents of the lab's directory. You're now ready to start coding to solve the lab. Note: You can use the `Open` button in the Learn OSX app to the same effect. 
2. Alternatively, from a terminal window, you can type the `learn open` command which will open up your current lab 

You'll notice that on Learn, the light labelled "Fork" will turn green after you've opened up a lab.

So what's going on here? Behind the scenes, the Learn CLI is (1) forking this lab's repository on Github (2) running `git clone` to clone the contents down to your computer (3) running `cd` to change directory into the lab's directory then (4) opening your text editor so you can get to work. 

## Running Tests with `learn`

When you're working on a lab, you'll write code in your text editor according to the instructions on Learn. The way you'll know you've solved the lab correctly, is by running the "test suite" on your computer and aim to get all tests to pass. 

We'll get into something called "test-driven development" (TDD) later, but in short, all you need to know is that TDD is the way modern, professional software is built. The idea is to define, up front, the set of things your program should do, then write your code, then verify (by running tests) that your code actually does the things your program should do. Put another way, tests allow you to confirm that your code works—by being very explicit about what we mean by "works". 

In order to confirm that you've solved a lab correctly on learn, you need to run through the following sequence:

1. Run `learn test` (or use the even shorter `learn` command which does the same thing) to invoke the test suite
2. Read the output. If tests are failing, go back to your code and fix it until all tests pass. Once all tests pass, you're ready to move on. 

You'll notice that on Learn, the light labelled "Local build" will turn green after you've got all tests to pass. 

## Submitting your solution with `learn submit`

Once you've written the code that solves a lab, and confirmed that your solution is correct using the `learn` command, you then need to submit your solution to Learn so that you can get credit for completion and move on to the next lesson. 

In order to submit your solution to Learn, just run `learn submit`. That's all it takes.

You'll notice that on Learn, the light labelled "Pull Request" will turn green when your code has been submitted. 

So what's going on here? Behind the scenes, the Learn CLI is (1) using the `git push` command to push your coded solution to Github and (2) opening up a Pull Request on the original (un-forked) repository. The cool thing about this is that in the process of solving labs on Learn, you're building up your Github profile!
