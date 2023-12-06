# Inspired Code

Here is a list of inspired codes that influenced me throughhout my coding Journey.

## 1. Building a JavaScript Chatbot Inspired Codes

**Source:** [HTML Goodies - Basic Chatbot in JavaScript](https://www.htmlgoodies.com/javascript/basic-chatbot-in-javascript/)

### Overview

For one of my initial assignments, I embarked on the challenge of constructing a JavaScript-based chatbot application. This marked my first solo exploration into JavaScript, and I sought inspiration on essential aspects such as iterating through responses, tracking user progress, and best practices for response storage. The journey led me to a foundational example that significantly influenced my approach.

Some Questions included:

- How do I iterate through layers of potential responses
- How do I save where the user is in the chatbot questioning
- What are best practices when it comes to storing potential responses

### Findings

The example app, comprising standard `index.html` and `index.css` files, featured functions using if statements to handle diverse user responses. This approach, though seemingly obvious, provided valuable insights into JavaScript practices. The use of if statements to check user responses made it an ideal starting point for my first JavaScript project.

![Website info screenshot](images/Building-a-JavaScript-Chatbot.png)

> Screen shot inspired code from HTML Goodies

## Implementation

In my chatbot app, I applied lessons from the example code. I utilized a numbering system and conditions to track the user's progress. Leveraging React, I enhanced UI interaction. Below is a snippet demonstrating conditional responses based on user input:

```javascript

const getBotReply = (msg) => {
  if (msg.toLowerCase() === "random") {
    return `And your random movie is .........drum roll........ ${getRandomMovie(randomMovies)}!`
  }

  if (msg.toLowerCase() === "restart") {
    return "Hi there my name is Archie and my job is to help you find the perfect animated moie for you to watch. <br /><br />But firstly, what is your Name?"
  }

  if (level === 1) {
      level ++;
      name = msg;
      return `Thats a nice name ${name}, nice to meet you! Now please tell me do you enjoy watching animated films?`;
  }

  if (level === 2) {
    level ++;
    if (msg.toLowerCase() === yesValues) {
        // path = "yes";
        return "GREAT... I mean *ahem* great. So do you like movies that will bring on the waterworks or movies that make you laugh?";
      }

      if (msg.toLowerCase() === noValues) {
        // path = "no";
        return "Well this is a bit awkward... kinda defeats my purpose completely but you do you I guess. Sorry I cant be much help to you today. If you want to restart type 'restart' or type 'random' for a randomly selected movie";
      }

  }
```
