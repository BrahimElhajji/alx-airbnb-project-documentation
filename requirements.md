# 📄 Backend Feature Requirement Specifications

This document defines the technical and functional requirements for key backend features of the Airbnb Clone project.

---

## 1. 🧑‍💻 User Authentication

### Description
Handles user registration, login, and authentication using JWT tokens.

### API Endpoints
- `POST /api/register` – Register a new user
- `POST /api/login` – Log in an existing user
- `GET /api/user/profile` – Get authenticated user’s profile (JWT required)

### Request/Response Examples

#### POST /api/register
**Request:**
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "securePassword123"
}
```
Response:

```
{
  "message": "User registered successfully",
  "token": "JWT_TOKEN"
}
```
POST /api/login
Request:

```
{
  "email": "john@example.com",
  "password": "securePassword123"
}
```
Response:

```
{
  "message": "Login successful",
  "token": "JWT_TOKEN"
}
```

### Validation Rules
- Email must be in valid format and unique.

- Password must be at least 8 characters.

- All fields are required.

### Performance Criteria
- Login and registration should respond within 1 second.

- Token expires in 1 hour; refresh token supported.

## 2. 🏠 Property Management
### Description
- Hosts can list, edit, retrieve, and delete property listings.

### API Endpoints
- `POST /api/properties` – Create new property

- `GET /api/properties/:id` – View property details

- `PUT /api/properties/:id` – Update property

- `DELETE /api/properties/:id` – Delete property

### Request/Response Examples
#### POST /api/properties
Request:

```
{
  "title": "Cozy Apartment",
  "description": "A lovely two-bedroom apartment.",
  "location": "Berlin",
  "price": 75,
  "amenities": ["Wi-Fi", "Kitchen"],
  "available_from": "2025-06-01",
  "available_to": "2025-09-01"
}
```
Response:

```
{
  "message": "Property listed successfully",
  "property_id": "abc123"
}
```
### Validation Rules
- title, location, and price are required.

- price must be a positive number.

- Dates must be in YYYY-MM-DD format and logically valid.

### Performance Criteria
- Response time ≤ 2 seconds.

- Scales to 1000+ concurrent listings.

## 3. 📅 Booking System
### Description
- Allows guests to book properties for a selected date range.

### API Endpoints
- `POST /api/bookings` – Create new booking

- `GET /api/bookings/:id` – View booking details

- `DELETE /api/bookings/:id` – Cancel a booking

### Request/Response Examples
#### POST /api/bookings
Request:

```
{
  "property_id": "abc123",
  "guest_id": "user456",
  "start_date": "2025-07-10",
  "end_date": "2025-07-15"
}
```
Response:

```
{
  "message": "Booking confirmed",
  "booking_id": "b789xyz"
}
```
### Validation Rules
- Booking must be within property's available dates.

- No overlapping bookings for the same property.

- Start date must be before end date.

### Performance Criteria
- Response time ≤ 2 seconds.

- Prevent double booking using database transactions.

## 🔒 General Backend Requirements
- All endpoints must use HTTPS.

- Standard HTTP status codes should be used:

- 200 OK, 201 Created, 400 Bad Request, 401 Unauthorized, 404 Not Found

- Input should be validated both client- and server-side.

- All passwords must be hashed (e.g., bcrypt).

- JWT secret keys must be stored securely in environment variables.
