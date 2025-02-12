# Maryland Meals AI API Documentation

## Base URL

```
http://<your-server-url>:<PORT>
```

## Endpoints

### 1. Generate Images

**Endpoint:**

```
POST /generate-images
```

**Description:**
Fetches images of foods and returns them as base64-encoded strings.

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
  "1": "data:image/jpeg;base64,/9j/...",
  "2": "data:image/jpeg;base64,/9j/..."
}
```

---

### 2. Detect Foods

**Endpoint:**

```
POST /detect-foods
```

**Description:**
Detects food items present in an image.

**Request Body (JSON):**

```json
{
  "imageUrl": "https://example.com/food.jpg",
  "menu": "Pizza, Burger, Salad"
}
```

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
Generates a meal plan based on user context.

**Request Body (JSON):**

```json
{
  "context": "A vegetarian looking for a high-protein diet."
}
```

**Response (JSON):**

```json
{
  "plan": "Your meal plan includes lentil soup, grilled tofu, and quinoa salad."
}
```

---

### 4. Get Description

**Endpoint:**

```
POST /get-description
```

**Description:**
Generates a short description of a dish based on its name and ingredients.

**Request Body (JSON):**

```json
{
  "context": "Spaghetti Carbonara with eggs, pancetta, and Parmesan cheese."
}
```

**Response (JSON):**

```json
{
  "plan": "A classic Italian pasta dish with a creamy, savory sauce."
}
```

---

## Error Handling

If an error occurs, the API returns a 400 or 500 response:

```json
{
  "error": "An error occurred while processing the request"
}
```

Ensure that all required fields are included in the request body.
