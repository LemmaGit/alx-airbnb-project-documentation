# Backend Feature Requirements

This document outlines the technical and functional requirements for key backend features of the Airbnb Clone.

---

## 1. User Authentication

### API Endpoints

- `POST /api/auth/register`
- `POST /api/auth/login`

### Input

- **Register**: `{ name, email, password }`
- **Login**: `{ email, password }`

### Output

- JWT token, user info

### Validation Rules

- Email must be valid and unique
- Password: min 6 characters

### Performance Criteria

- Token generation within 300ms
- 95% success rate under load

---

## 2. Property Management

### API Endpoints

- `POST /api/properties`
- `GET /api/properties`
- `PUT /api/properties/:id`
- `DELETE /api/properties/:id`

### Input

- `{ title, description, location, price, amenities, images }`

### Output

- Created/Updated property object

### Validation Rules

- Title: required, max 100 chars
- Price: numeric, > 0
- Images: min 1 image required

### Performance Criteria

- CRUD operations must complete under 500ms

---

## 3. Booking System

### API Endpoints

- `POST /api/bookings`
- `GET /api/bookings/:id`
- `DELETE /api/bookings/:id`

### Input

- `{ propertyId, checkIn, checkOut, guests }`

### Output

- Booking confirmation object

### Validation Rules

- checkIn < checkOut
- No overlapping bookings for same property

### Performance Criteria

- Booking creation under 400ms
- Date conflict checks < 150ms
