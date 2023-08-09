# Python Simulation Project

## Contents

1. [Overview](#overview)
2. [Skills to Use](#skills-to-use)
3. [Project Ideas](#project-ideas)
4. [Sample Projects](#sample-projects)
5. [Specs and Requirements](#specs-and-requirements)
6. [Extensions](#extensions)

## Overview

Computer simulations are some of the most cost-efficient ways to test our hypotheses about how to approach real-world problems, and Python is really well suited to these sorts of tasks. Consider, for example, a grocery store that is considering switching from individual checkout lines to a single line that feeds to the next ready register. The cost of actually implementing that change to see if it's better would be massive. You'd need to re-design the checkout areas, re-train employees, and come up with a way of measuring the efficiency of this new system.

A Python simulation can be used to do some initial testing of this new system without requiring any physical changes to the store. This simulation can also be used to test edge cases that might be harder or riskier to create in a real-world test, like when the store is short-staffed, or when half the registers break down.

In this project, you'll think about a real-world situation that you'd like to simulate. As you create your simulation, your goal is to either solve a problem or answer a question related to your situation. In order to do the necessary comparing and contrasting, you'll need to code out at least two approaches to the situation (e.g. one unified line).

**Before starting to code your actual simulation, you must create your input data**. You can do this with a Python script, with an ai-powered tool, or by sourcing real-world data. Once you have at least three different inputs, you may begin coding your simulation(s).

As you build out your simulation, please a list of the assumptions you make in the `assumptions.md` file. For example, the assumption that each food item a customer purchases takes 3 seconds to scan would result in a radically different outcome than if each item is assumed to take 20 seconds to scan.

## Skills to Use

Unless you feel strongly that your project idea does not require it, aim to demonstrate / practice the following skills if possible. This is a valuable opportunity to use some of the approaches that interviewers will most expect to see.

##### Object-Oriented Programming

Most simulations include at least one real-world item or concept that is best rendered as a class in Python. If it makes sense to utilize a class in your simulation, be attentive to each of the following:

- You'll likely need at least two instances of a class you make.
- You'll want the class to have at least one instance method.

##### Recursive Functions

This may or may not fit into your simulation, as not every real world phenomenon can be addressed recursively, but it comes up in most interview situations, so if you see an opportunity to implement a recursive function, you should do so.

- Be sure to clearly implement the base case first.

## Project Ideas

These ideas are designed to get you started, but they are by no means your only options. Please talk with your group about a situation you'd like to simulate and what questions you'd hope to answer. The sky really is the limit here, so please don't let these questions limit you.

With that said, you're encouraged to think about the situation, problem, approaches, and sample data in the way that these examples shown here before beginning to make sure you and your collaborators are on the same page.

### Example 1: Grocery Check-Out

---

**Situation**: In a grocery store, we want customers to be able to check out and pay for their items as quickly as possible, so we'll use a simulation to decide the best way to structure the checkout experience.

**Problem to solve / question to answer**: There are three common ways to do checkout at a grocery store, so we'll model all three to determine which is best:

1. Multiple open registers with individual lines - customers can line up in whichever one seems the shortest and wait their turn. This can backfire if one register ends up having more complicated products to ring than others.
2. An express "10 items or less" lane - this means that anyone who is doing a super light shopping trip can have a faster checkout experience, meaning that only those whose orders take a long time to ring up will have to wait a long time.
3. Multiple open registers fed by a single line - by using one single line, each open register will be filled by the person next in line. This means that no one will end up waiting longer than they have to by getting in "the wrong line" because they misjudged how much time the line would take.

**Sample input data shape**: A list of customers who would like to check out. We'll create three versions - one with 10 customers, one with 25, and one with 100, and measure the average, minimum, and maximum times each customer spent waiting

```
customer_id, number_of_items, cash_or_credit
1, 12, CASH
2, 22, CREDIT
3, 3, CREDIT
4, 35, CREDIT
5, 2, CASH
```

### Example 2: Card Game

---

**Situation**: The card game "war" can be pretty boring - two players each play the top card from their deck, the higher card wins, and the winner acquires both cards. However, there's a variant where you're allowed to either shuffle or sort your deck, and are allowed to draw from either the top or bottom of you deck. Is one strategy more likely to win a simplified game of war?

**Problem to solve / question to answer**: If your partner plays war the traditional way, will you perform better or worse if you sort your deck? Are you more likely to win if you pull from the top of your sorted deck? Or if you pull from the bottom?

**Sample data shape**: This is a simplified, shuffled deck of cards. We'll deal the deck into two halves and simulate a game of war.

```
10D,8H,9S,4H,10S,2H,2C,7S,6S,5C,10C,8D,8C,KS,6H,7C,7D,4S,6C,AC,AD,QD,3C,5H,4C,QC,4D,9H,KC,KD,2D,3S,AS,5D,JD,JC,3H,QH,9C,QS,3D,7H,8S,9D,6D,KH,5S,2S,JS,5C,10H,JD
```

### Example 3: Multiple-Choice Test Guessing Penalty

---

**Situation**: In school, sometimes teachers institute a "guessing" penalty, where you lose 1/4 of a point for each question you get wrong on a multiple-choice test. This guessing penalty is also used on the SAT, but it's interesting to consider the degree to which this guessing penalty impacts scores. In theory, it's meant to neutralize any advantage a student might get by being lucky on a few questions, but in practice it'd be helpful to know whether it's better to leave those questions blank, or if it's better to guess anyways. It's also interesting from a teacher's perspective whether the guessing penalty adversely impacts some students more than others.

**Problem to solve / question to answer**: Is there a guessing strategy that works better than others? Does the guessing penalty change which strategy is best?

**Sample data shape**: We'll need two sets of data - one "answer key" to a test of 100 multiple-choice questions that might look something like this:

```
1D
2E
3C
4A
5B
6A
7D
```

We'll also need a list of students who are varying levels of "prepared" for the test, and who each have a different strategy of guessing when they don't know an answer.

```
student_id, percent_prepared, guessing_strategy
1, 100, ALL_D
2, 90, RANDOM
3, 70, RANDOM
4, 50, RANDOM
5, 50, ALL_D
6  70, LEAVE_BLANK
7, 0, RANDOM
8, 0, ALL_D
9, 0, ZIGZAG_PATTERN
```

## Specs and Requirements

Whether or not you use one of the sample ideas, please be sure your project does all the following:

1. Your project should begin with at least three different sample inputs that you've either generated programmatically, created with a tool, or found in real-world data.
2. Your simulation should utilize at least two different solutions to the problem you've created. The goal is to determine which of two approaches is better, so you need at least two solutions in order to be able to do that.
3. Based on your simulation, you should be able to recommend which of two approaches you'd recommend in a real-world implementation.
4. Your assumptions document should be clear about the assumptions you used to simplify a complex real-world situation into a repeatable simulation.
5. Your solutions do not need to be optimized for time or space complexity, but since most interviewers will ask about these things, please be prepared to describe (at least to some degree) the time and space complexity of each of your simulations.
