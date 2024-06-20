# User Information Fetcher

This project is a simple web application that allows users to fetch and display the first name of a user from the ReqRes API by entering a user ID. The application is built using HTML and JavaScript, utilizing an XMLHttpRequest to communicate with the API.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Code Explanation](#code-explanation)
- [Contributing](#contributing)
- [License](#license)

## Introduction

The User Information Fetcher is a basic example of how to use JavaScript to make HTTP requests and manipulate the DOM based on the response data. It demonstrates the following:
- Capturing user input
- Making GET requests to an external API
- Parsing JSON responses
- Updating HTML content dynamically

## Features

- Fetches user information from the ReqRes API.
- Displays the first name of the user based on the provided user ID.

## Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

You need a web browser to run the application.

## Usage

1. Open the `javascript.html` file in your browser.
2. Enter a user ID in the input field.
3. Click the "Submit" button.
4. The application will display the first name of the user corresponding to the entered ID.

## Code Explanation

### HTML Structure

The HTML file consists of:
- A paragraph element to display the fetched user name.
- An input field for the user to enter the user ID.
- A button to trigger the user information fetch.

```html
<p id="output">Default text</p>
<input id="user_number">
<button onclick="update_user()">Submit</button>
```

### JavaScript Functionality

The JavaScript code includes:
- `update_user` function: This function captures the user ID entered, makes an HTTP GET request to the ReqRes API, and updates the paragraph text with the user's first name upon receiving a successful response.

```javascript
function update_user(){
    user_number = document.getElementById("user_number").value;
    httpRequest = new XMLHttpRequest();
    httpRequest.open("GET", "https://reqres.in/api/users/"+user_number);
    httpRequest.send();

    httpRequest.onreadystatechange = function(){
        if(this.readyState == 4 && this.status == 200)
        {
            user_data = JSON.parse(this.responseText);
            document.getElementById("output").innerHTML = user_data.data.first_name;
        }
    }
}
```

### Key Elements

- `XMLHttpRequest`: Used to create a new HTTP request.
- `open()`: Initializes the request.
- `send()`: Sends the request to the server.
- `onreadystatechange`: An event handler called whenever the `readyState` property changes.
- `readyState` and `status`: Properties used to determine if the request was successful.
- `JSON.parse()`: Parses the JSON response from the API.



## Conclusion
Developers are requested to use this code section according to their project needs. Thank you!
