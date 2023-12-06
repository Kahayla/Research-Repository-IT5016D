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

> _Screen shot inspired code from [HTML Goodies](https://www.htmlgoodies.com/javascript/basic-chatbot-in-javascript/)_

### Implementation

In my chatbot app, I applied lessons from the example code. I utilized a numbering system and conditions to track the user's progress. Leveraging React, I enhanced UI interaction. Below is a snippet demonstrating conditional responses based on user input:

```javascript
const getBotReply = (msg) => {
  if (msg.toLowerCase() === "random") {
    return `And your random movie is .........drum roll........ ${getRandomMovie(
      randomMovies
    )}!`;
  }

  if (msg.toLowerCase() === "restart") {
    return "Hi there my name is Archie and my job is to help you find the perfect animated moie for you to watch. <br /><br />But firstly, what is your Name?";
  }

  if (level === 1) {
    level++;
    name = msg;
    return `Thats a nice name ${name}, nice to meet you! Now please tell me do you enjoy watching animated films?`;
  }

  if (level === 2) {
    level++;
    if (msg.toLowerCase() === yesValues) {
      // path = "yes";
      return "GREAT... I mean *ahem* great. So do you like movies that will bring on the waterworks or movies that make you laugh?";
    }

    if (msg.toLowerCase() === noValues) {
      // path = "no";
      return "Well this is a bit awkward... kinda defeats my purpose completely but you do you I guess. Sorry I cant be much help to you today. If you want to restart type 'restart' or type 'random' for a randomly selected movie";
    }
  }
};
```

> _This code is directly from my chatbot repository_

### Findings

This example that my source uses containing global array variables declared at the start of the application containing a bunch of string values, again this is an obvious way to structure the application but as I was a spring chicken in this space I was looking for inspiration as to how I might structure my app.

![Website info screenshot](images/Programming-Bot-Responses-in-JavaScript.png)

> _Screen shot inspired code from [HTML Goodies](https://www.htmlgoodies.com/javascript/basic-chatbot-in-javascript/)_

### Implenetation

In my app I followed the theme of using global variables to store strings which I could refer to later on in my app. I ended up using an object structure which meant all my chatbot responses were included in the object properties. However I did use the array variable to store all my potential end result answers. Because the array was at the top level this means at any stage the chatbot could’ve responded with any of the possible answers contained in the array. I also decided to include possible user answers in OR string variables meaning the user could respond with “yes” “yep” “yeah” etc at any point in the app and the response would be considered as valid this prevents repeated code throughout the app.

```javascript
const yesValues = "yes" || "yup" || "yeah" || "y";
const noValues = "no" || "nope" || "n" || "nah";
const randomMovies = [
  "Shrek",
  "Ice Age",
  "Kung-Fu Panda",
  "Up",
  "Onward",
  "Big Hero 6",
  "Finding Nemo",
  "The Lion King",
  "Inside Out",
];

let level = 1;
let path;
let name;
```

> _This code is directly from my chatbot repository_
