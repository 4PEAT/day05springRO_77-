
---

### ✅ Task 1: Implement a `Brand` entity
- Create a new entity called `Brand` with fields like `id` and `name`.
- Establish a one-to-many relationship between `Brand` and `Product`.
- Implement full CRUD support for the `Brand` entity using controller, service, and repository layers.

---

### ✅ Task 2: Create a custom endpoint to list products by category
- Add a new endpoint to retrieve all products that belong to a specific category, using its `id`.
- The response should return only the products linked to the given category.

---

### ✅ Task 3: Add validation before deleting a category
- Prevent deletion of a category if it still contains any products.
- If products exist, return a meaningful error message via a custom exception and handle it properly in the controller.


### ✅ Task 4: Create a custom search endpoint for products by name
- Add an endpoint that returns all products whose names contain a given keyword (case-insensitive).
- Use a query method in the `ProductRepository`.

---

### ✅ Task 5: Add price filtering
- Create an endpoint to get all products within a given price range (min and max).
- Use request parameters like `/api/products/filter?min=10&max=50`.

---

### ✅ Task 6: Count total products in a category
- Add an endpoint that returns the number of products associated with a specific category.

---

### ✅ Task 7: Add timestamps to products
- Add `createdAt` and `updatedAt` fields to the `Product` entity.
- Automatically populate them using annotations or logic in the service layer.

---

### ✅ Task 8: Return all categories with their products
- Create an endpoint that returns all categories including the list of products under each (nested JSON).
- Avoid infinite recursion with Jackson annotations.

---

### ✅ Task 9: Implement a product bulk creation endpoint
- Add a POST endpoint that accepts a list of products in the request body and saves them all in one go.

---

### ✅ Task 10: Add basic validation for product creation
- Ensure the product’s name is not empty and price is positive before saving.
- If validation fails, return a 400 Bad Request with a clear error message.
