# The Learn CLI Workflow

## Overview

The deep integration of Learn, Git, and GitHub makes it possible for all of the work you do on Learn to be stored and version-controlled by GitHub behind the scenes, just like professional software.

We'll eventually introduce you to all of the Git mechanics that make this work. But for the purposes of getting started on Learn quickly, we've created some convenient tools to make it easier to move through our curriculum.

You'll use the same workflow to solve every lab on Learn. It involves 3 steps:

1. Opening the lab.
2. Working on the lab until you get all tests to pass.
3. Submitting your solution.

Let's walk through the process. For now, just read along. **You don't need to actually perform any actions right now**. You'll have the opportunity to practice this entire workflow in the next lesson!

## Opening a Lab

**Key takeaway: Use the Open button to get started with a lab.**

Getting to work on a new lab is very simple: you'll want to simply click the "Open" button on the toolbar.

![Learn Open](https://s3-us-west-2.amazonaws.com/curriculum-content/intro-to-learn/learn_workflow_open.png)

This automatically will invoke the Learn CLI (a command line application we built to make things) and will get this lab onto your computer in a state where you can start working on it. You may see your Terminal flash open then your text editor will open with the content of the lab.

Pro Tip #1: If you ever need to re-open a lab you've previously opened, you can just hit the Open button again.  

Pro Tip #2: Another way to open the current lab you should be working on, is to use the Learn CLI yourself by running the `learn open` command from your terminal. This is exactly what the Open button is doing behind the scenes.

![Learn Open](https://s3-us-west-2.amazonaws.com/curriculum-content/intro-to-learn/learn_workflow_terminal.png) 

### What does the Open button do?

As described above, when you hit the Open button in your browser, Learn actually invokes the Learn CLI and runs the `learn open` command on your computer which does the following:

1. It uses the GitHub API to "fork" the lab on your behalf. This means it creates a copy of the lab's repository for you and associates it with your GitHub account.
2. It then "clones" that copy of the repo down to your computer automatically, so that you have a local copy of the source code to work with. This is what you'll be using to solve the lab.
3. It then "cd's" into the lab's directory on your computer and opens your text editor with the contents of the lab

![Work mode](https://dl.dropboxusercontent.com/s/je5pazo2edy5cwl/2015-09-30%20at%207.34%20PM.png)

This setup, a terminal in the lab's directory and the lab directory open in an editor like Sublime or Atom, that's the state you want to be in when working on a lab on Learn. It means you're ready.

## Solving a Lab

** Key takeaway: use the `learn` command to run tests until they all pass. **

### Overview

Once you've opened your lab locally, you'll be ready to start solving it. This is the fun part!

All of the labs on Learn are written with an RSpec test suite that you can use to confirm that you've fulfilled the requirements of the lab. RSpec is a testing library that ruby developers use everyday, so again, as you work on Learn, you're also learning the same tools and workflows that developers use.

## Test Driven Workflow

When you work on a lab, we recommend the following workflow:

### 1. Reading the README

Read the lab's README on Learn and get a sense of what the lab is about and what it is asking you to build. Read the entire README and then work on the lab and as you hit hurdles you'll have a context for where to look for clues and hints in the README.

### 2. Run the tests with `learn`

Before doing any work, run the test suite from your local clone with the `learn` CLI command. From your terminal, in a lab's directory, run `learn`, you'll see something similar to:

![Failing Test](https://dl.dropboxusercontent.com/s/0ik01a1urmuw7o6/2015-09-30%20at%207.46%20PM.png)

I know error messages or failure messages are intimidating, but try to read them. Developers are detectives, constantly sleuthing for the bug that's the culprit. Errors and failures are our clues, they illuminate the path forward.

We know that the idea of "things being broken" is frightening at first. Broken things are stressful and frustrating! But guess what? As an engineer, as a programmer, the default state of anything you work on is broken. The things you are programming are always broken. Get used to it. Your job is to fix broken things. You can do it. If your code isn't broken, if your code works, you are no longer programming. Your job is done. Things work. Embrace the errors. The obstacle is the way.

### 3. Read the tests

Read the test suite in `spec/`. Open up the lab in your text editor, open the files in the `spec` directory that are not named `spec_helper.rb`. `spec_helper.rb` is a helper file to configure your tests which you can ignore. Any file in `spec` that ends in `_spec.rb` though is a test file and while testing code and RSpec are advanced, we believe the semantics are easy to understand, the meaning of the test is comprehensible, even if the code is not.

For example, soon you'll be solving your first lab. The lab includes a file `spec/first_lab_spec.rb`. The contents will be:

```ruby
describe 'First Lab:' do
  it 'you made a change' do
    new_file_made = Dir["*"].size > 5
    file_edited = !File.read("./edit-me.txt").empty?
    expect((new_file_made || file_edited)).to be_truthy, "Make sure you have added a new file or edited edit-me.txt"
  end
end
```

You haven't even written a line of code yet and we're asking you to read some very abstract and complex code and try to reach for any footing or understanding. We believe in you. We believe you can infer and deduce and understand a bit of the code above, even with no experience. Your mind is  incredibly powerful. Challenge yourself and confront the unknown. That's how learning works.

Beyond all the syntax and code above, can you decipher what we're asking for? What the lab requires you to do? How the test works? Again, even if you only get 10% of the expectations of the test, that's still something. And while you do that, 4 things will happen.

1. You'll have 10% more understanding of how to solve the lab.

2. You'll get better at reading tests and we bet that the next test you read you'll get 12% of it and constantly see improvement through old fashioned practice and determination.

3. Almost unconsciously, like Mr. Miyagi in the Karate Kid, you'll actually learn how to read and write tests proficiently, "Wax on, wax off" style.

	![Wax On, Wax Off](https://38.media.tumblr.com/a5dc9f34d87226be8f31f5c982c8af7b/tumblr_mklzm4VeUq1rwt2uzo1_500.gif)

4. You'll have learned Test-Driven-Development, TDD, one of the most sought after skills of a professional developer.

This cycle, reviewing the README, running the tests, reading failure messages, reading the tests, editing your code, and trying it all again, is how you are supposed to code, it's what programmers do all day. We break things, we define the error with a test, we fix the code, we pass the test, we repeat.

### 4. Write Your Code

After forking and cloning the lab, opening the lab in a text editor, reading the README, running the test suite, reading the errors, and reading the tests themselves in `spec`, you're ready to code. You've armed yourself with every weapon available in the arsenal of your intellect and we know you can program triumphantly.

You should understand the point of the lab.

You should be able to identify the objectives and topics the lab is exercising so you can google for more information.

You should know the expected behavior or outcome of the solution.

You should know what files you need to create or edit.

You should know what those files and code should define, provide, and do.

You should constantly save and test your code with every significant change.

You should read error messages and glean insight into the solution with every new failure.

You should keep on trying until you get it working. It doesn't matter how many times you fail as long as it is one less than the times you tried.

You should ask for help on Learn.

Programming is never about getting it all right at once. Programming is like solving a puzzle, you don't try to put it together immediately, you approach it one piece at a time. The workflow we're describing optimizes this process, trial and error, attempts and feedback, insight through failure. Most of our time as programmers is spent staring at error message and code wondering, "Hmm".

#### Programming in Movies vs Real Life
<iframe src="https://vine.co/v/hPXTA6l9AqQ/embed/simple" width="600" height="600" frameborder="0"></iframe>

### 5. Pass your local tests with `learn`

Follow this workflow: running tests, reading errors, writing code, saving code, running tests, reading errors, consulting the README, googling for more context on a topic, writing more code, saving the code, running the tests again, reading errors, and repeat. You'll get it, you'll surprise yourself and find a confidence within you. And if you're stuck or tired and just need some help, Ask a Question and the Learn community will be there for you.

Eventually your local tests will pass and Learn will indicate your success.
![Pass](https://s3-us-west-2.amazonaws.com/curriculum-content/intro-to-learn/learn_workflow_local.png)

On the left is a passing test run in the terminal. On the right is what the right column in Learn looks like for a passing local test (which we currently call a "Local Build").

When your local tests are passing, you'll be ready to submit the lab.

## Submitting a Lab

**Key takeaway: use the `learn submit` command to submit your solution.**

Once you've written the code that solves a lab, and confirmed that your solution is correct using the `learn` command, you then need to submit your solution to Learn so that you can get credit for completion and move on to the next lesson.

In order to submit your solution to Learn, from the lab's directory in your Terminal, you will just need to run:

```
learn submit
```

That's all it takes, you can run `learn submit` from any lab directory and your solution will be submitted to Learn for review.

![learn submit](http://learn-co-videos.s3.amazonaws.com/learn-co-orientation/learn-submit-cli-osx.gif)

You'll notice that on Learn, the light labelled "Pull Request" will turn green when your code has been submitted.

![PR](https://s3-us-west-2.amazonaws.com/curriculum-content/intro-to-learn/learn_workflow_pr.png)

## What does `learn submit` do?

The `learn submit` and the Learn CLI automate all the low-level `git` interactions. When you type `learn submit`, here's what happens:

1. Your local changes are staged via `git add .` and committed via `git commit -am`.
2. Your local commits are pushed to your fork on GitHub with `git push`
3. A Pull Request from your fork is opened.

## Conclusion

To summarize, the workflow you'll be using to solve labs on Learn:

Use the Open button (or `learn open`) to fork and clone your lab locally so you can work on it.
Use `learn test` to run your local tests.
Use `learn submit` to submit your solution.**

You are now ready to practice the Learn workflow with your first lab! Congratulations!

<a href='https://learn.co/lessons/learn-cli-workflow-osx' data-visibility='hidden'>View this lesson on Learn.co</a>
