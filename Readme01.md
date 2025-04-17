

## ✅ Book Lending REST API Task

---

### 🎯 Objective

Create a Spring Boot REST API that allows you to manage a collection of books in memory.

You will:
- Store books in a `Set<Book>` (no database)
- Generate IDs using a simple `long counter`
- Implement basic REST operations (CRUD + borrow/return)
- Test your API using Postman

---

### 📦 Data Model – `Book`

Each book must have the following fields:

| Field     | Type     | Description                    |
|-----------|----------|--------------------------------|
| `id`      | `long`   | Auto-generated unique ID       |
| `title`   | `String` | Book title (required)          |
| `author`  | `String` | Book author (required)         |
| `borrowed`| `boolean`| Default: `false`               |

**Note:** You must override `equals()` and `hashCode()` in `Book` based only on the `id`.

---

### 🧠 Storage Details

- Use a `Set<Book>` to store all books in memory
- Use a `long counter` to assign unique IDs (e.g. `++counter`)
- No database, no external services

---

### 🧪 API Endpoints

| Method | Endpoint                  | Description                              | Status |
|--------|---------------------------|------------------------------------------|--------|
| `POST` | `/api/books`              | Create a new book                        | `201` / `409` |
| `GET`  | `/api/books`              | Get all books                            | `200` |
| `GET`  | `/api/books/{id}`         | Get a book by ID                         | `200` / `404` |
| `PUT`  | `/api/books/{id}/borrow`  | Mark a book as borrowed                  | `200` / `409` / `404` |
| `PUT`  | `/api/books/{id}/return`  | Mark a book as returned                  | `200` / `409` / `404` |
| `DELETE` | `/api/books/{id}`       | Delete a book by ID                      | `200` / `404` |

---

### 🧪 Postman Examples

#### ✅ Add a book
```
POST /api/books
Content-Type: application/json

{
  "title": "Clean Code",
  "author": "Robert C. Martin"
}
```

#### ✅ Borrow a book
```
PUT /api/books/1/borrow
```

#### ✅ Return a book
```
PUT /api/books/1/return
```

#### ✅ Get all books
```
GET /api/books
```

#### ✅ Get book by ID
```
GET /api/books/1
```

#### ✅ Delete book
```
DELETE /api/books/1
```

---

### ✅ BONUS Challenge (Optional)

- Add a default value using `@Value` from `application.properties` for missing title or author
- Add a `maxBooks` limit (e.g., 10 books max) — return `403 Forbidden` if exceeded

