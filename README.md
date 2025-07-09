# titan_hardware

## https://youtu.be/kxK2_W2LHPY

### The Titan Hardware project is a web-based hardware shop developed using the Flask framework in Python. The goal of the system is to simulate an online hardware shopping experience that allows users to browse hardware products, view product details, add items to a cart, and complete an order through a simple and interactive checkout process. The project was designed with usability and simplicity in mind, targeting hardware customers in Kenya and potentially extending to a broader audience. It demonstrates how a basic e-commerce application can be built using Flask, integrating backend logic with HTML templates and database operations.

# Functionality Overview
# Titan Hardware replicates the fundamental features of an online shop:
1.	Homepage and Product Listings
# On the homepage (home.html), all available hardware products are listed in a visually appealing format. Each product displays its name, price, and a link to view more details. The design encourages users to explore the catalog and interact with products using simple mouse clicks.
2.	Product Details View
Clicking on a product takes the user to a dedicated product detail page (product_detail.html). This page provides detailed information about the item, including price, stock availability, and an image. It includes an option to place an order, which adds the item to the shopping cart. Before the order is confirmed, the user is asked for confirmation via a browser popup (“Are you sure you want to place an order for this item?”), simulating a real purchase decision.
3.	Shopping Cart
The cart view allows users to see all products they’ve added along with the quantities. This is implemented using Flask sessions to temporarily store cart data while the user is navigating through the site. Users can remove items from the cart or proceed to the checkout page from here.
4.	Checkout Page
The checkout functionality is a crucial part of the project. It’s accessible from the navigation bar or after viewing the cart. The form collects essential user details such as:
o	Full Name
o	Email Address
o	Delivery Location
o	Expected Delivery Date
Upon submitting the form, the data is validated using Flask-WTF and saved to a SQLite database. A confirmation message is shown to the user on the confirmation.html page, confirming that the order was placed successfully.
5.	About Page & Navigation
The about.html page introduces the project and company, giving a brief background and purpose. The navigation menu in the base.html layout allows users to easily move between Home, About, Cart, and Checkout pages. A footer provides contact information, email, phone number, and the company’s location in Nairobi, Kenya.

Technologies Used
•	Flask: The main framework used to build the server-side logic.
•	Python: The programming language used for backend development.
•	Flask-WTF: For form handling and CSRF protection.
•	SQLite: The database used to store product, order, and customer information.
•	Jinja2: Flask’s built-in templating engine to render dynamic content.
•	HTML/CSS/JavaScript: For designing the user interface, form interactivity, and page layout.
•	Bootstrap (Optional): Can be added to enhance the responsiveness and appearance of the pages.

Backend Structure
The backend logic consists of several routes defined in routes.py:
•	/ – Displays the home page with a list of products.
•	/product/<int:product_id> – Shows the product detail view.
•	/add_to_cart/<product_id> – Adds a product to the cart using Flask sessions.
•	/cart – Displays current items in the shopping cart.
•	/checkout – Displays the checkout form and processes orders.
•	/about – Displays the about page.
The models (e.g., Product, Order, OrderItem) define the database schema and relationships between products and orders. Flask SQLAlchemy is used to interact with the SQLite database.

Database Schema (Simplified)
•	Product: id, name, price, stock, image_url
•	Order: id, customer_name, customer_email, location, expected_date, order_date
•	OrderItem: id, order_id, product_id, quantity

Unique Features
•	Session-based Cart: Users can add products to their cart without logging in.
•	Confirmation Dialog: Before placing an order, the user is prompted with a browser confirmation message.
•	Dynamic Routing: Each product has its own detailed page rendered with URL parameters.
•	CSRF Protection and Validation: Flask-WTF protects the checkout form and ensures valid inputs.
•	Structured UI: The base layout (base.html) includes a common header and footer, and each page extends this template using Jinja2 blocks.

How to Use the Project
1.	Launch the application by running:
             flask run
2.	Visit http://127.0.0.1:5000/ in your browser.
3.	Browse products and click “Add to Cart” or “Place Order”.
4.	Go to the cart to review selected items.
5.	Proceed to the checkout form and enter your details.
6.	Submit the form to confirm the order and view the confirmation page.

Future Improvements
•	Add user authentication and login system.
•	Enable email notifications for order confirmations.
•	Implement admin panel to manage products and orders.
•	Add product categories and search functionality.
•	Support multiple payment options (e.g., M-Pesa).

This project demonstrates practical web development skills with Flask and provides a functional example of a simple e-commerce platform. It can be deployed locally or extended for real use cases with minimal upgrades.

# project
# project
