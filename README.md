# Course Recommender System

A Python-based course recommendation API that uses content-based filtering to recommend courses based on a user's interests.

## Features

- Course recommendations through a Flask REST API
- Content-based recommendation using TF-IDF
- Cosine similarity for relevance scoring
- MongoDB integration for user and course data
- JSON API responses

## Tech Stack

- Python
- Flask
- MongoDB
- PyMongo
- Scikit-learn
- TF-IDF
- Cosine Similarity

## Project Structure

```text
course-recommender/
├── course_recommender.py
├── requirements.txt
├── .gitignore
└── LICENSE
```

## Installation

```bash
git clone <your-repository-url>
cd course-recommender
python -m venv venv
```

### Activate the virtual environment

**Windows:**
```bash
venv\Scripts\activate
```

**macOS/Linux:**
```bash
source venv/bin/activate
```

### Install dependencies

```bash
pip install -r requirements.txt
```

## Configuration

Configure the required MongoDB connection details in the application before running the project.

Do not commit passwords, API keys, connection strings, or other secrets to the repository.

## Run the Application

```bash
python course_recommender.py
```

The Flask API runs on port `5000` by default.

## API Usage

### Recommendations Endpoint

**Method:** `GET`

**Endpoint:**
```text
/recommendations
```

**Query Parameter:**
- `user_email` — email address used to retrieve the user's interests

Example:

```text
http://127.0.0.1:5000/recommendations?user_email=testuser@gmail.com
```

### Response

The endpoint returns a JSON object containing recommended courses.

```json
{
  "recommendedCourses": [
    {
      "title": "Web Development for Beginners",
      "description": "A web development course for beginners",
      "domain": "web development",
      "price": 0
    }
  ]
}
```

## How It Works

1. The API receives a user's email.
2. User interests are retrieved from MongoDB.
3. Course information is processed using TF-IDF vectorization.
4. Cosine similarity is calculated between user interests and course content.
5. The most relevant courses are returned as JSON.



This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
