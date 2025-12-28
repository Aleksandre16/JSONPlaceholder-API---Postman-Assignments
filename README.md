# 🚀 JSONPlaceholder API Testing Suite

![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)
![API Testing](https://img.shields.io/badge/Testing-Automated-green?style=for-the-badge)
![JSONPlaceholder](https://img.shields.io/badge/API-JSONPlaceholder-blue?style=for-the-badge)

A comprehensive API testing collection built for the **JSONPlaceholder API**. This suite automates CRUD operations, manages dynamic data chaining, and performs rigorous schema validation.

## 📂 Project Structure

The collection `Aleksandre_JSONPlaceholder_Assignment` is organized into four logical modules:

### 1️⃣ User Data Operations (`01_User_Operations`)
* **GET Users:** Filters response data for companies containing the string "Group".
* **POST New User:** Uses a **Pre-request Script** to generate unique `generated_email` and `generated_username` variables.
* **Dynamic Chaining:** Manually initializes `user_id` in the Pre-request script to ensure workflow continuity.

### 2️⃣ Post Operations (`02_Post_Operations`)
* **GET Posts by User:** Validates that all returned posts strictly belong to the specified `user_id`.
* **PUT Update Post:** Updates post details and verifies the response matches the `updated_title` and `updated_body` environment variables.
* **DELETE Post:** Confirms successful resource removal and verifies an empty JSON response.

### 3️⃣ Comment Operations (`03_Comment_Operations`)
* **GET Comments:** Performs **Regex validation** on all email fields within the comment array.
* **POST New Comment:** Generates unique content and ensures data types (ID as number, body as string) are correct.

### 4️⃣ Album & Photo Chain (`04_Album_Photo_Operations`)
* **Request Chaining:** Dynamically captures `album_id` to fetch associated photo data.
* **Data Verification:** Includes a specific test to verify the album contains exactly **50 photos**.
* **Media Validation:** Validates that `url` and `thumbnailUrl` follow the correct `https://` format.

---

## ⚙️ Environment Configuration

The `JSONPlaceholder_Environment` file manages the following key variables:

| Variable | Description |
| :--- | :--- |
| `base_url` | `https://jsonplaceholder.typicode.com` |
| `user_id` | Currently active user ID for testing |
| `post_id` | Currently active post ID for updates/deletion |
| `album_id` | Target ID for album and photo retrieval |
| `current_timestamp` | Used for generating unique, non-colliding data |

---

## 🛠️ Global Testing Logic

The collection utilizes **Collection-Level Scripts** to ensure every request meets these standards:

* **Performance:** Every response must be received in under **5000ms**.
* **Content-Type:** Ensures the header consistently returns `application/json`.
* **Error Handling:** A global script monitors status codes ≥ 400 to ensure the API handles errors gracefully (Not Found, Bad Request, etc.).
* **Schema Integrity:** Every request validates that returned IDs are numbers and text fields are strings.

---
# 🎓

> **Project for Principles of Test Automation Engineering ** > **Institution:** Caucasus University  
> **Lecturer:** Nika Tukashvili
