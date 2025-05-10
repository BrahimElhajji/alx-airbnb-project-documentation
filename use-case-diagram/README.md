# Airbnb Clone Backend - Use Case Diagram

## 📌 Objective

This document presents the use case diagram for the backend of the Airbnb Clone project. The diagram illustrates how different types of users (actors) interact with the system's features and functionalities.

## 👥 Actors

- **Guest**: A user who can search, book properties, and leave reviews.
- **Host**: A user who can list and manage properties.
- **Admin**: A system administrator who monitors and manages the platform.

## 🎯 Key Use Cases

| Use Case              | Description                                                                 |
|-----------------------|-----------------------------------------------------------------------------|
| Register/Login        | Users (Guest, Host, Admin) authenticate using email/password or OAuth.     |
| View Listings         | Guests can search for properties using filters (location, price, etc.).    |
| Book Property         | Guests can book available listings for specific dates.                     |
| Cancel Booking        | Guests can cancel bookings based on policies.                              |
| Make Payments         | Guests pay for bookings using integrated payment gateways.                 |
| Add/Edit/Delete Listing | Hosts can create and manage property listings.                           |
| Leave Review          | Guests can review properties after their stay.                             |
| Manage Users/Listings | Admin can view, update, or deactivate users and property listings.         |

### Guest
- Register/Login
- Search for Properties
- Book a Property
- Cancel Booking
- Make Payment
- Leave Review
- Receive Notifications

### Host
- Register/Login
- Manage Listings (Create, Edit, Delete)
- Cancel Booking
- Receive Notifications

### Admin
- Manage Users
- Manage Listings
- Access Booking Data
- Monitor Payments
- View and Moderate Reviews

## 📌 Diagram

 ![ChatGPT Image 10 mai 2025, 20_47_31](https://github.com/user-attachments/assets/ba74a5df-b32b-4509-b95c-7e5d129e6207)



## 📝 Notes

- Each actor may share some functionalities (e.g., both Guests and Hosts must login), which is why certain use cases connect to multiple users.
- Admin functionalities are kept minimal for clarity but may expand in a production system.

