🐦 Social Media Tweet API (Flask + MySQL)

A RESTful backend API that simulates core Twitter-like functionality.
Built using Flask, MySQL, and UUID-based tweet identification, supporting full CRUD operations on tweets.
_________________________________________________________________________________________________________

🚀 Features
•	Post a tweet with unique tweet_id
•	Fetch all tweets (latest first)
•	Fetch tweets by specific user
•	Update tweet content
•	Delete tweet
•	Server-side timestamp handling
•	Input validation & HTTP status codes
_________________________________________________________________________________________________________

🛠️ Tech Stack
•	Backend: Python (Flask)
•	Database: MySQL
•	Connector: mysql-connector-python
•	ID Generation: UUID
•	API Style: REST
_________________________________________________________________________________________________________

📂 Database Schema (Expected)
Database: social_media
Table: tweets

Columns:
- tweet_id (VARCHAR / UUID, PRIMARY KEY)
- user_name (VARCHAR)
- tweet_text (TEXT)
- created_at (DATETIME)
_________________________________________________________________________________________________________

📌 API Endpoints

1️⃣ Post a Tweet
POST /tweet
Request Body
{
  "user_name": "john",
  "message": "Hello World"
}
Response
{
  "message": "Tweet posted successfully!"
}
_________________________________________________________________________________________________________

2️⃣ Get All Tweets
GET /tweet/get
Returns all tweets ordered by latest first.
_________________________________________________________________________________________________________

3️⃣ Get Tweets by User
GET /tweets/get/<user_name>
Fetches tweets for a specific user.
_________________________________________________________________________________________________________

4️⃣ Update a Tweet
PUT /tweet/<tweet_id>
Request Body
{
  "message": "Updated tweet content"
}
_________________________________________________________________________________________________________

5️⃣ Delete a Tweet
DELETE /tweet/<tweet_id>
Deletes tweet permanently.
_________________________________________________________________________________________________________

⚙️ How to Run Locally
1.	Clone the repository
2.	Install dependencies
3.	pip install flask mysql-connector-python
4.	Create MySQL database and table
5.	Update DB credentials in app.py
6.	Run the app
7.	python app.py
8.	API runs on
9.	http://127.0.0.1:5000
_________________________________________________________________________________________________________

📈 Design Decisions
•	UUID used instead of auto-increment IDs for scalability
•	created_at updated on edit to track last modification
•	Simple architecture focused on API clarity
•	Clean separation of endpoints for maintainability
__________________________________________________________________________________________________________

🔮 Future Enhancements
•	User authentication (JWT)
•	Likes & comments
•	Pagination
•	Soft deletes
•	Rate limiting
•	Dockerization
