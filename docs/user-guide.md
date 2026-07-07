# API Reference

## Configure Stock Alert

**Endpoint**

```
POST /api/v1/alerts/config
```

---

## Authentication

This endpoint requires Bearer Token authentication.

### Header

```
Authorization: Bearer YOUR_ACCESS_TOKEN
```

---

## Request Body

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| product_id | String | Yes | Unique product identifier |
| threshold_limit | Integer | Yes | Minimum stock level before alert |
| notification_email | String | Yes | Email address to receive alerts |
| is_active | Boolean | Yes | Enables or disables the alert |

---

## Example Request

```json
{
  "product_id": "PRD-1001",
  "threshold_limit": 20,
  "notification_email": "manager@example.com",
  "is_active": true
}
```

---

## Success Response (201 Created)

```json
{
  "message": "Alert configuration created successfully.",
  "status": 201,
  "data": {
    "product_id": "PRD-1001",
    "threshold_limit": 20,
    "notification_email": "manager@example.com",
    "is_active": true
  }
}
```

---

## Error Response (400 Bad Request)

```json
{
  "status": 400,
  "message": "Validation failed.",
  "errors": [
    {
      "field": "threshold_limit",
      "message": "Threshold limit must be greater than zero."
    }
  ]
}
```
