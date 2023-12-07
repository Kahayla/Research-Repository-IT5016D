# Interesting Codes

Here is a list of interesting codes that I found helpful or rather interesting throughout my coding journey.

## 1. Exploring Random Value Selection in JavaScript

**Source:** [Stack Overflow - Get a random item from a JavaScript array](https://stackoverflow.com/questions/5915096/get-a-random-item-from-a-javascript-array)

### Overview

In the realm of my chatbot project, I encountered a unique challenge—implementing a 'special functionality' that involved selecting random values from an array. Delving into the vast world of JavaScript, I stumbled upon an insightful solution on Stack Overflow. The code snippet showcased the utilization of `Math.random` to extract a random value from an array, laying the foundation for a feature-rich chatbot.

### Implementaion

In my app I used this function by grabbing the user’s response, if user’s response = “random” run the function over the array

```javascript
const yesValues = "yes" || "yup" || "yeah" || "y";
const noValues = "no" || "nope" || "n" || "nah";
const randomMovies = ["Shrek", "Ice Age", "Kung-Fu Panda", "Up", "Onward", "Big Hero 6", "Finding Nemo", "The Lion King", "Inside Out"];

let level = 1;
let path;
let name;

const getRandomMovie = (randomMovieArray) => {
  const randomIndex = Math.floor(Math.random() * randomMovieArray.length);
  const randomMovie = randomMovieArray[randomIndex];
  return randomMovie;
}

const getBotReply = (msg) => {
  if (msg.toLowerCase() === "random") {
    return `And your random movie is .........drum roll........ ${getRandomMovie(randomMovies)}!`
  }
```
