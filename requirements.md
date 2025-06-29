# Airbnb Clone Backend – Requirements Specifications

## 1. User Authentication

### 📌 API Endpoints
- `POST /api/v1/register` → Register a new user.
- `POST /api/v1/login` → Login an existing user.

### 📥 Input Specifications
- Registration: `name`, `email`, `password`, `role` (guest, host)
- Login: `email`, `password`

### 📤 Output Specifications
- Registration: Success message, JWT token
- Login: JWT token, user role

### ✅ Validation Rules
- Email must be in valid format and unique.
- Password must be at least 6 characters.
- Role must be either `guest`, `host`, or `admin`.

### ⚙️ Performance Criteria
- Response time: Less than 1 second.
- Handle at least 100 concurrent login requests.

---

## 2. Property Management

### 📌 API Endpoints
- `POST /api/v1/properties` → Create a new property listing.
- `GET /api/v1/properties` → View property listings.
- `PUT /api/v1/properties/{id}` → Edit property.
- `DELETE /api/v1/properties/{id}` → Delete property.

### 📥 Input Specifications
- Property: `title`, `description`, `location`, `price`, `amenities`, `availability`

### 📤 Output Specifications
- Success message, property data.

### ✅ Validation Rules
- Title must not be empty.
- Price must be a positive number.
- Location and availability must be provided.

### ⚙️ Performance Criteria
- Response time: Less than 2 seconds.
- Efficient querying for large datasets using pagination.

---

## 3. Booking System

### 📌 API Endpoints
- `POST /api/v1/bookings` → Create a new booking.
- `GET /api/v1/bookings` → View user bookings.
- `DELETE /api/v1/bookings/{id}` → Cancel booking.

### 📥 Input Specifications
- Booking: `property_id`, `user_id`, `start_date`, `end_date`

### 📤 Output Specifications
- Success message, booking details.

### ✅ Validation Rules
- Dates must be valid and not overlap existing bookings.
- Property must exist and be available.

### ⚙️ Performance Criteria
- Real-time availability checking.
- Fast booking confirmation (under 2 seconds).
