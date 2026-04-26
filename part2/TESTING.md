# API Testing Report

This document outlines the black-box testing performed on the HBnB API using cURL and Swagger UI.

## 1. User Endpoints

### Create a User (POST)
**Command:**
curl -X POST [http://127.0.0.1:5000/api/v1/users/](http://127.0.0.1:5000/api/v1/users/) -H "Content-Type: application/json" -d '{"first_name": "Alice", "last_name": "Smith", "email": "alice@example.com"}'

**Expected Outcome:** `201 Created` with a JSON payload containing the user's `id`.

### Retrieve All Users (GET)
**Command:**
curl -X GET [http://127.0.0.1:5000/api/v1/users/](http://127.0.0.1:5000/api/v1/users/)

**Expected Outcome:** `200 OK` with a JSON list of user objects.

## 2. Validation Testing (Error Handling)

### Invalid Place Price (POST)
**Command:**
curl -X POST [http://127.0.0.1:5000/api/v1/places/](http://127.0.0.1:5000/api/v1/places/) -H "Content-Type: application/json" -d '{"title": "Beach House", "price": -50, "latitude": 34.0, "longitude": -118.0, "owner_id": "VALID_ID"}'

**Expected Outcome:** `400 Bad Request` with `{"error": "Price must be a positive number."}`

## 3. Review Endpoints

### Delete a Review (DELETE)
**Command:**
curl -X DELETE [http://127.0.0.1:5000/api/v1/reviews/](http://127.0.0.1:5000/api/v1/reviews/)<review_id>

**Expected Outcome:** `200 OK` with `{"message": "Review deleted successfully"}`.
