# REST-API
1. What is REST?
ANS .REST is basically a way to structure APIs so they’re easy to use and follow. It uses standard HTTP methods like GET,          POST, PUT, and DELETE to work with data. Everything is stateless, meaning each request is independent, and data is            usually sent in JSON format.

2. What are HTTP methods and what are they used for?
ANS. They’re like actions you perform on data:
     GET – to fetch data (like getting a list of books)
     POST – to add new data (like adding a new book)
     PUT – to update existing data
     DELETE – to remove data

3. How do you handle routes in Express?
ANS. In Express, you set up routes to respond to different requests. For example:
     js
    app.get('/books', (req, res) => {
    res.json(books);});
    Each route listens for a specific method and URL, and then runs a function to send back a response.

4. What is middleware in Express?
ANS. Middleware is like a middleman that runs before your actual route logic. It can do things like parse JSON, log requests,      or handle errors. A common one is:
     js
     app.use(express.json());
     That lets you read JSON data from the request body.

6. How do you parse JSON in Express?
ANS. Just use:
     js
     app.use(express.json());
     It’s built-in and makes sure you can access req.body when someone sends JSON data.

6. What status codes do you use for CRUD?
ANS. Here are the usual ones:
    200 – OK (for GET, PUT, DELETE)
    201 – Created (for POST)
    400 – Bad Request (if something’s missing)
    404 – Not Found (if the item doesn’t exist)

7. How would you handle errors in Express?
ANS.I usually check if something’s wrong and send a proper response:
    js
    if (!book) {
    return res.status(404).json({ error: 'Book not found' });}
    You can also create a custom error handler at the end of your routes to catch unexpected issues.

8. What is CORS?
ANS. CORS is a browser security thing. It decides if a site can access data from another site. If you’re building an API that      others will use, you might need to enable CORS using the cors package:
     js
     const cors = require('cors');
     app.use(cors());

9. What are request and response objects in Express?
ANS. req is what the client sends (like data, parameters, etc.)
     res is what you send back (like a message or data)
    Example:
    js
    app.post('/books', (req, res) => {
    const book = req.body;
    res.status(201).json(book);});

   10. How do you test API endpoints?
ANS. I use Postman. You just choose the method (GET, POST, etc.), enter the URL, add any data, and hit send. It shows you the      response and status code. Super handy for checking if your API works.
