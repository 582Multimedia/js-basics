# Class 3

## Async / Await

The `async function` declaration creates a binding of a new async function to a given name. The `await` keyword is permitted within the function body, enabling asynchronous, promise-based behavior to be written in a cleaner style and avoiding the need to explicitly configure promise chains.

You can also define async functions using the `async function` expression.

```js
function resolveAfter2Seconds() {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve("resolved");
    }, 2000);
  });
}

async function asyncCall() {
  console.log("calling");
  const result = await resolveAfter2Seconds();
  console.log(result);
  // Expected output: "resolved"
}

asyncCall();
```

## Event Handling

[Event handling (overview)](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers)

Events are signals fired inside the browser window that notify of changes in the browser or operating system environment. Programmers can create event handler code that will run when an event fires, allowing web pages to respond appropriately to change.

### Basic event handling - avoid

We can add basic event handling like this:

```js
function greet(event) {
  console.log("greet:", event);
}

window.onclick = greet;
```

### addEventListener() - recommended

Instead of doing it that way, we should use the **recommended** way, using the `addEventListener` method:

```js
function greet(event) {
  console.log("greet:", event);
}

window.addEventListener("click", greet);
```

The `addEventListener()` method of the EventTarget interface sets up a function that will be called whenever the specified event is delivered to the target.

Common targets are Element, or its children, Document, and Window, but the target may be any object that supports events.

### arrow function shorthand

We can shorthand it with an arrow function:

```js
window.addEventListener("click", (event) => console.log("greet:", event));
```

## Fetch API

[Using the Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)

The Fetch API provides a JavaScript interface for making HTTP requests and processing the responses.

With the Fetch API, you make a request by calling fetch(), which is available as a global function in both window and worker contexts. You pass it a Request object or a string containing the URL to fetch, along with an optional argument to configure the request.

The `fetch()` function returns a Promise which is fulfilled with a Response object representing the server's response. You can then check the request status and extract the body of the response in various formats, including text and JSON, by calling the appropriate method on the response.

Here's a minimal function that uses fetch() to retrieve some JSON data from a server:

```js
async function getData() {
  const url = "https://dummyjson.com/test";
  try {
    const response = await fetch(url);
    if (!response.ok) {
      throw new Error(`Response status: ${response.status}`);
    }

    const json = await response.json();
    console.log(json);
  } catch (error) {
    console.error(error.message);
  }
}
```

## Modules

[JavaScript modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)
