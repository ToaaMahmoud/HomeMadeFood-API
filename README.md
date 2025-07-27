# Homemade Food API
Backend system for a platform connecting users with home-made-food chefs to order and manage meals.

- Users can view meals, add them to a cart, place orders, and track their status.  
- Chefs can manage their meal listings, receive orders, and update order statuses.
- The system includes secure authentication, role-based access control, and OTP-based password recovery.
---

## Features

- User registration, login, logout with JWT
- OTP-based password reset flow
- Cart per user (add/remove/update meals)
- Order creation with total price auto-calculated
- Role-based access: users, chefs, admins
- Meal image uploads to Cloudinary
- Email notifications using Nodemailer
- Search by Image: upload an image to find visually similar meals
- Personalized Meal Recommendations: meals suggested automatically based on user's order history


---

## Use Cases

1. A user signs up, logs in, selects meals, adds them to cart, sets a delivery address, and places an order.
2. A user reviews and rates a meal after receiving the order.
3. A user updates their profile or deletes their account.
4. A user forgets their password, resets it using OTP sent to their email.
5. A user uploads an image of food to discover similar meals available in the platform.  
6. A user receives personalized meal recommendations based on their previous orders.
7. A chef adds new meals and tracks incoming orders, updating their statuses.


## API Endpoints
The backend is RESTful and organized into logical modules.  
All protected routes require **JWT authentication** and **role-based access control**.

### 🔐 Auth
- `POST /auth/login` – Log in with email and password  
- `PATCH /auth/verify-email` – Verify user or chef email  
- `POST /auth/send-otp` – Send OTP to email for password reset  
- `POST /auth/token` – Refresh access token  
- `PATCH /auth/change-password` – Change password using OTP  
- `POST /auth/google` – Login with Google  
- `POST /auth/facebook` – Login with Facebook  
- `POST /auth/signup-user` – Register as user  
- `POST /auth/signup-chef` – Register as chef  

### 📍 Address (User)
- `POST /address` – Add address  
- `GET /address` – Get all addresses for user  
- `PATCH /address` – Update address  
- `DELETE /address` – Delete address  

### 🍽️ Meals
- `GET /meals` – Get all meals  
- `GET /meals/:id` – Get single meal details  
- `POST /meals/favorite` – Add to favorites  
- `GET /meals/favorites` – Get favorite meals  
- `DELETE /meals/favorite/:id` – Remove from favorites  

### 👤 Account

#### For Users:
- `PUT /account/user/profile` – Update profile  
- `POST /account/user/follow-chef` – Follow a chef  
- `GET /account/user/followed-chefs` – Get followed chefs  
- `GET /account/user/chefs` – Get all chefs  
- `GET /account/user/nearby-chefs` – Get nearby chefs  

#### For Chefs:
- `PATCH /account/chef/email` – Update email  
- `DELETE /account/chef` – Delete chef account  
- `GET /account/chef/profile` – Get chef profile  
- `PUT /account/chef/role` – Switch user/chef role  
- `PATCH /account/chef/password` – Change password  

### 🛒 Cart
- `POST /cart` – Add meal to cart  
- `GET /cart` – Get all cart items  
- `GET /cart/:id` – Get specific cart item  
- `PUT /cart/:id` – Update cart item  
- `DELETE /cart/:id` – Delete meal from cart  
- `PUT /cart/checkout` – Checkout cart (create order)  
- `DELETE /cart/admin-clear` – Admin-only: clear user's cart  

### 📦 Orders
- `GET /orders/user` – Get all orders for the user  
- `GET /orders/chef` – Get all orders for the chef  
- `PUT /orders/accept/:id` – Chef accepts an order  
- `PUT /orders/status/:id` – Chef updates order status  
- `DELETE /orders/:id` – Cancel order (user or chef)  
- `GET /orders/:id/full` – Get full order with meals & details  
- `GET /orders/:id` – Get basic order details  

### 📝 Reviews
- `POST /reviews` – Add or update review  
- `GET /reviews/meal/:mealId` – Get reviews for a specific meal  
- `GET /reviews/:reviewId` – Get a specific review by ID  
- `GET /reviews/user` – Get all reviews written by the user  
- `DELETE /reviews/:id` – Delete a review  

### 🔍 Search & Recommendations

- `POST /similar` – Upload an image and receive visually similar meals.
- `POST /get-recommended-meals` – Get personalized meal recommendations based on user history.

---

## 🎥 Demo Videos

These demos show backend-driven flows including authentication, cart management, address handling, meal reviews, image-based search, and personalized recommendations:

- [Mobile App](https://drive.google.com/drive/folders/13_v2j7ZWdWIqzTQdYKsf-PIGfN9O_uwY?usp=sharing)
- [Web Platform](https://drive.google.com/drive/u/0/folders/1MVoOaqc0TrCnlYS17yjOGFg2IwSH2C_a)
---


## API Documentation
Explore and test the complete API using the Postman collection:  
[View Full API Documentation on Postman](https://documenter.getpostman.com/view/41764030/2sB2j4hBbn)


## Backend Team

This backend system was developed by:
- [Toaa Mahmoud](https://github.com/ToaaMahmoud)
- [Khaled Saeed](https://github.com/K7413dS433d)
- [Tasneem Helmy](https://github.com/Tasneemhelmy)

