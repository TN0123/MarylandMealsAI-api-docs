# Maryland Meals AI API Documentation

## Base URL

```
http://your-server-url/
```

## Endpoints

### 1. Generate Food Images

**Endpoint:**

```
POST /generate-images
```

**Description:**
Generates base64-encoded images of food items using Google Image Search.

**Request Body (JSON):**

```json
{
  "1": "Pizza",
  "2": "Burger"
}
```

**Response (JSON):**

```json
{
  "1": "data:image/jpeg;base64,...",
  "2": "data:image/jpeg;base64,..."
}
```

---

### 2. Detect Foods in an Image

**Endpoint:**

```
POST /detect-foods
```

**Description:**
Detects food items in an image provided by the user.

**Request Body (JSON):**

```json
{
  "imageUrl": "https://example.com/image.jpg",
  "imageBase64": "data:image/jpeg;base64,...",
  "menu": "Pizza, Burger, Salad"
}
```

**Note:** The user can provide either `imageUrl` or `imageBase64`, but at least one must be included.

**Response (JSON):**

```json
{
  "foods": "Pizza, Burger"
}
```

---

### 3. Meal Recommender

**Endpoint:**

```
POST /meal-recommender
```

**Description:**
Generates a meal plan based on user-provided context.

**Request Body (JSON):**

```json
{
  "context": "A 30-year-old vegetarian looking for healthy meal options."
}
```

**Response (JSON):**

```json
{
  "plan": "Breakfast: Oatmeal with fruits, Lunch: Grilled vegetable salad, Dinner: Lentil soup."
}
```

---

### 4. Get Food Description

**Endpoint:**

```
POST /get-description
```

**Description:**
Generates a short description of a dish based on its ingredients and name.

**Request Body (JSON):**

```json
{
  "context": "Pasta with tomato sauce and basil"
}
```

**Response (JSON):**

```json
{
  "plan": "A classic Italian dish with rich tomato sauce and fresh basil."
}
```

---

## Error Handling

All endpoints return an error response in case of failure:

```json
{
  "error": "An error occurred while processing the request"
}
```

---
