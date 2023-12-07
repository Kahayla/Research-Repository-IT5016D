# Inspired Code

Here is a list of inspired codes that influenced me throughhout my coding Journey.

### Overview

1. Building a JavaScript Chatbot Inspired Codes
2. Exploring ReactJS Hooks: `useState` and `useEffect`
3. Navigating Database Queries in Middleware

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

> _This code is directly from my [chatbot repository](https://github.com/Kahayla/build-a-chatbot/blob/main/01-project---build-a-chatbot-Kahayla-main%202/Submission/script.js)_

### Findings

This example that my source uses containing global array variables declared at the start of the application containing a bunch of string values, again this is an obvious way to structure the application but as I was a spring chicken in this space I was looking for inspiration as to how I might structure my app.

![Website info screenshot](images/Programming-Bot-Responses-in-JavaScript.png)

> _Screen shot inspired code from [HTML Goodies](https://www.htmlgoodies.com/javascript/basic-chatbot-in-javascript/)_

### Implementation

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

> _This code is directly from my [chatbot repository](https://github.com/Kahayla/build-a-chatbot/blob/main/01-project---build-a-chatbot-Kahayla-main%202/Submission/script.js)_

## 2. Exploring ReactJS Hooks: `useState` and `useEffect`

**Source:** [codedamn - Understanding useState and useEffect Hooks in ReactJS](https://codedamn.com/news/reactjs/usestate-and-useeffect-hooks)

### Overview

My fascination with ReactJS, particularly its JSX implementation for HTML-looking components, led me to delve into React-specific functionalities. Among these, the `useEffect` and `useState` hooks caught my attention. The `useEffect` function intrigued me for its role in managing side effects within the app. Contrary to a common misconception, it extends beyond the initial app loading, enabling execution based on various conditions throughout the component's lifecycle. This flexibility proves beneficial for tasks like data fetching during mounting or cleanup during unmounting. Additionally, `useState` facilitates the management of local state in functional components, triggering re-renders upon state updates. Together, `useEffect` and `useState` provide an efficient and controlled approach to state and side effect management in React applications.

### Findings

In the provided resource, a simple example demonstrates the usage of the `useEffect` and `useState` hooks to `fetch` and store data. The example focuses on a getUsers function with a `fetch` request inside a `useEffect`. Upon receiving data, the `useState `hook is employed to store the users' data within a users state using setUsers. A similar approach was adopted in my online shop app, where I utilised the same method to `fetch` and store product data.

![Website info screenshot](images/Basic-usage-of-useEffect.png)

> _Screen shot inspired code from [codedamn](https://codedamn.com/news/reactjs/usestate-and-useeffect-hooks)_

### Implementation

In my online shop app I used the same method to get my products by using a `fetch` request inside the `useEffect` and then using the `useStat`e hook to store that data

```javascript
getProducts.js;

const getProducts = async () => {
  // Use the following URL for your fetch request
  const url = `${process.env.REACT_APP_API_URL}/products`;

  // Fetch products and prices from the Stripe API
  const response = await fetch(url);
  console.log(response);
  const products = await response.json();
  console.log(products);
  return products;
};

export { getProducts };
```

> _This code is directly from my [keyme online shop repository](https://github.com/Kahayla/keyme-online-shop/blob/main/01-project---online-shop-individual-Kahayla-main/src/services/getProducts.js)_

```javascript
App.js;

// The function that makes the fetch request to the Products API
import { getProducts } from "./services/getProducts";

function App() {
  const [products, setProducts] = useState([]);

  useEffect(() => {
    const loadData = async () => {
      const products = await getProducts();
      setProducts(products);
    };
    loadData();
  }, []);

  return (
    <div className="container">
      {products.map((product) => (
        <div key={product.id} className="product-grid">
          <img src={product.images} alt={product.name} />
          <h2>{product.name}</h2>
          <p className="description">{product.description}</p>
          <p className="price">${product.prices[0].unit_amount / 100}</p>
          <button
            onClick={() => {
              checkout(product.prices[0].id);
            }}
          >
            Buy Now
          </button>
        </div>
      ))}
    </div>
  );
}
```

> _This code is directly from my [keyme online shop repository](https://github.com/Kahayla/keyme-online-shop/blob/main/01-project---online-shop-individual-Kahayla-main/src/App.js)_

## 3. Navigating Database Queries in Middleware

**Source:** [DZone - The Complete Tutorial on the Top 5 Ways to Query Your PostgreSQL Database in Node.js](https://dzone.com/articles/the-complete-tutorial-on-the-top-5-ways-to-query-y)

### Overview

When developing applications, the common practice is to connect them to external APIs, leveraging data managed on the API's end. However, when the requirement arose to set up my own database, I found myself uncertain about connecting my middleware to query the database effectively and retrieve the necessary data for display in my app.

### Findings

In the process of addressing this challenge, I explored the usage of the 'pg' package, which facilitates sending SQL commands to the database. The key insight was employing the db.query function to execute SQL commands, enabling the definition of the desired data to be retrieved.

![Webiste info screenshot](images/dzone-site.png)

> _Screen shot inspired code from [dzone](https://dzone.com/articles/the-complete-tutorial-on-the-top-5-ways-to-query-y)_

### Implementation

In my application, I utilised the following code:

```javascript
Copy code
const db = require("../db");

const getProducts = async () => {
  try {
    const result = await db.query(
      `SELECT
          p.id,
          p.name,
          p.description,
          p.price,
          pc.name AS "categoryName",
          pi.name AS "imageName",
          pi.description AS "imageDescription"
        FROM product p
        LEFT JOIN product_category pc ON p.product_category_id = pc.id
        LEFT JOIN product_image pi ON p.product_image_id = pi.id
        ORDER BY p.id
      `
    );
    return result.rows;
  } catch (error) {
    throw Error(error);
  }
};

const getPagedProductsSQL = `
SELECT
    p.id,
    p.name,
    p.description,
    p.price,
    pc.name AS "categoryName",
    pi.name AS "imageName",
    pi.description AS "imageDescription",
    pd.value AS "discountValue",
    dt.type AS "discountTypeName"
FROM product p
LEFT JOIN product_category pc ON p.product_category_id = pc.id
LEFT JOIN product_image pi ON p.product_image_id = pi.id
LEFT JOIN product_discount pd ON p.id = pd.product_id
LEFT JOIN discount_type dt ON dt.id = pd.discount_type_id
ORDER BY p.id
LIMIT $1 OFFSET $2;
`;

const getPagedProducts = async (limit, page) => {
  try {
    if (page <= 0 || !page) {
      throw new Error("Page number must be greater than 0");
    }

    const offset = limit * (page - 1);
    const { rows } = await db.query(getPagedProductsSQL, [limit, offset]);
    return rows;
  } catch (error) {
    throw Error(error);
  }
};

const getTotalProducts = async () => {
  try {
    const result = await db.query(`SELECT COUNT(*) as total FROM product`);
    return result.rows[0].total;
  } catch (error) {
    throw new Error(`Error fetching total products: ${error.message}`);
  }
};

module.exports = { getPagedProducts, getProducts, getTotalProducts };
```

> _This code is directly from my cat couture repository_

This code is based on the example, utilising middleware to directly query the database with SQL. This approach aligns with my preference as it allows for data validation directly via SQL commands in PostgreSQL. Additionally, it streamlines the integration between an app's database and frontend, simplifying the development process.
