# Technical-writing-assessment-
Technical writing internship assessment



API Reference

Endpoint

"POST /api/v1/alerts/config"

Description

The "POST /api/v1/alerts/config" endpoint creates a new stock alert configuration. It allows businesses to receive notifications when a product's inventory falls below a specified threshold.

---

Authentication

This endpoint requires Bearer Token Authentication.

Include the following header in your request:

Authorization: Bearer YOUR_ACCESS_TOKEN

---

Request Parameters

Parameter| Type| Required| Description
"product_id"| String| Yes| Unique identifier of the product.
"threshold_limit"| Integer| Yes| Minimum stock quantity before an alert is triggered.
"notification_email"| String| Yes| Email address that will receive the alert notification.
"is_active"| Boolean| Yes| Enables ("true") or disables ("false") the alert configuration.

---

Example Request

POST /api/v1/alerts/config
Authorization: Bearer YOUR_ACCESS_TOKEN
Content-Type: application/json

{
  "product_id": "PRD001",
  "threshold_limit": 20,
  "notification_email": "manager@example.com",
  "is_active": true
}

---

Success Response (201 Created)

{
  "message": "Alert configuration created successfully.",
  "status": 201
}

---

Error Response (400 Bad Request)

{
  "error": "Invalid request. Please check the required fields."
}

---

Conclusion

The "POST /api/v1/alerts/config" endpoint enables users to create stock alert configurations by submitting the required information. Ensure that all required fields are provided and that a valid Bearer Token is included before sending the request.

