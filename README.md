# E-commerce-web-page
File: server.js
const express = require("express");
const app = express();

// Use EJS template engine
app.set("view engine", "ejs");

// Route: Homepage
app.get("/", (req, res) => {
  const items = [
    { id: 1, name: "Laptop", price: 50000 },
    { id: 2, name: "Phone", price: 20000 },
    { id: 3, name: "Headphones", price: 2000 }
  ];
  res.render("home", { items });
});

// Start server
app.listen(3000, () => {
  console.log("E-commerce app running at http://localhost:3000");
});

File: views/home.ejs
<!DOCTYPE html>
<html>
<head>
  <title>E-commerce App</title>
</head>
<body>
  <h1>Welcome to My E-commerce Store</h1>
  <h2>Available Items</h2>
  <ul>
    <% items.forEach(item => { %>
      <li>
        <b><%= item.name %></b> - ₹<%= item.price %>
        <button>Add to Cart</button>
      </li>
    <% }) %>
  </ul>
</body>
</html>
