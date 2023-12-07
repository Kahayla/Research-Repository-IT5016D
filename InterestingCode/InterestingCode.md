# Interesting Codes

Here is a list of interesting codes that I found helpful or rather interesting throughout my coding journey.

### Overview

1. Exploring Random Value Selection in JavaScript
2. Exploring APIs: A Dive into Fun and Interesting Code
3. Streamlining Styles: A Dive into CSS Styling Helpers

## 1. Exploring Random Value Selection in JavaScript

**Source:** [Stack Overflow - Get a random item from a JavaScript array](https://stackoverflow.com/questions/5915096/get-a-random-item-from-a-javascript-array)

### Overview

In the realm of my chatbot project, I encountered a unique challenge—implementing a 'special functionality' that involved selecting random values from an array. Delving into the vast world of JavaScript, I stumbled upon an insightful solution on Stack Overflow. The code snippet showcased the utilization of `Math.random` to extract a random value from an array, laying the foundation for a feature-rich chatbot.

### Implementaion

In my app I used this function by grabbing the user’s response, if user’s response = “random” run the function over the array

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

const getRandomMovie = (randomMovieArray) => {
  const randomIndex = Math.floor(Math.random() * randomMovieArray.length);
  const randomMovie = randomMovieArray[randomIndex];
  return randomMovie;
};

const getBotReply = (msg) => {
  if (msg.toLowerCase() === "random") {
    return `And your random movie is .........drum roll........ ${getRandomMovie(
      randomMovies
    )}!`;
  }
};
```

> _This code is directly from my [chatbot](https://github.com/Kahayla/build-a-chatbot/blob/main/01-project---build-a-chatbot-Kahayla-main%202/Submission/script.js)repository_

## 2. Exploring APIs: A Dive into Fun and Interesting Code

Source: [Codex - 15 Fun and Interesting APIs to Use for Your Next Coding Project in 2022](https://medium.com/codex/15-fun-and-interesting-apis-to-use-for-your-next-coding-project-in-2022-86a4ff3a2742)

### Overview

Embarking on the exciting journey into the realm of APIs, this article chronicles my fascination with the simplicity of accessing a diverse range of data through fetch requests and URL endpoints. The exploration aims to showcase the potential of different data sources and their endpoints.

### Giphy API Adventure

Driven by my passion for creating animations and interactive apps, I, under the project name "Giphy App Sandbox," discovered the accessibility of Giphy's APIs. This personal exercise serves as a firsthand account of my experimentation.

Source: [Giphy API](https://developers.giphy.com/)

### Implementation and Security Measures

The article underlines my introduction to URL parameters as a means of filtering and focusing on specific data within the API responses. Additionally, the incorporation of API keys is highlighted, emphasizing the importance of securing API endpoints.

### My Giphy App Sandbox

Explore my personal exercise with the Giphy API by visiting the GitHub repository: [Giphy App Sandbox.](https://github.com/Kahayla/giphy-api-sandbox)
![giphy API exercise](images/Giphyapi.png)

## 3. Streamlining Styles: A Dive into CSS Styling Helpers

### Overview

Venturing into the realm of web styling can be overwhelming, with the myriad details involved in crafting the perfect look for a webpage and its components. Faced with this challenge, I wondered if there were code solutions built on top of JavaScript to enhance its functionality, similar to how React does. This led me to explore whether the same approach was taken with CSS.

### CSS Framework Exploration

I dedicated time to exploring various CSS frameworks, seeking tools that could streamline the styling process. These frameworks, or perhaps "flavors" of code, proved to be valuable resources. Why spend hours refining the appearance and behavior of a component when others have already done the heavy lifting?

### Bootstrap/React Bootstrap

Among the notable libraries, Bootstrap and its React counterpart stood out. These libraries offer pre-designed components and a style library, enabling quick and efficient application of styles without deviating from established design decisions.

Sources:

- [Bootstrap](https://getbootstrap.com/)
- [React Bootstrap](https://react-bootstrap.netlify.app/)

### Tailwind

While my exploration of Tailwind was more limited, I was captivated by its built-in styles. Andrew Watham's approach to implementing design alongside development resonated with me, making Tailwind an intriguing option.

Sources:

- [Refactoring U](https://www.refactoringui.com/)
- [Tailwind CSS](https://tailwindcss.com/)

  In summary, these CSS styling helpers have proven to be invaluable companions, offering ready-made solutions and empowering developers to focus on creating, rather than endlessly tweaking styles.
