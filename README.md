# Deep Music

**Deep Music** is a web-based application for **music mood classification and music recommendation based on user mood, favorite genres, and favorite artists**.

This project was developed as a **final project for a Deep Learning course**, with the goal of applying machine learning and deep learning techniques to a music recommendation system that can provide recommendations based on the user's current mood and listening preferences.

---

![preview](/public/Video-Project-10.gif)

## About

Deep Music is designed to provide relevant music playlist recommendations based on several factors:

* **User mood**
* **Frequently listened genres**
* **Favorite artists**

Users are periodically asked to provide their current mood through four categories:

* Happy
* Sad
* Calm
* Angry

Favorite artists are determined based on the artists marked as favorites by the user. Favorite genres are determined from the user's listening history. Whenever a user plays a song, the system retrieves the song's genre information and uses it to determine which genres the user listens to most frequently.

The system also provides a **music mood classification** feature that allows users to upload an audio file and receive a predicted mood classification.

The main goal of Deep Music is to provide **playlist recommendations that are relevant to the user's current mood and music preferences**.

> **Note:** This project was developed as a final project for a Deep Learning course. Due to project scope and development constraints, the application currently uses a single role that combines both **user and admin** functionality.

---

## Features

### Authentication

* User registration
* User login
* User logout

### Music Management

* Add songs
* Add artist information
* Play songs
* Create playlists
* Add songs to playlists

### Favorites

* Add artists to favorites
* Remove artists from favorites
* View favorite artists

### Mood

* Input user mood
* Classify the mood of an uploaded song
* Display mood classification results

### Music Preferences

* Determine the user's most frequently listened genres
* Determine favorite artists
* Use listening history as one of the factors for determining music preferences

### Recommendation

The recommendation system generates playlists based on a combination of:

```text
User Mood
    +
Favorite Genre
    +
Favorite Artist
    |
    v
Recommended Playlist
```

---

## System Architecture

Deep Music uses a separated frontend and backend architecture.

```text
+----------------------+
|       Frontend       |
|   Laravel + Blade    |
|   Vite + Tailwind    |
+----------+-----------+
           |
           | REST API
           v
+----------------------+
|       Backend        |
|       Flask          |
|       Python         |
+----------+-----------+
           |
           +--------------> Firebase
           |
           +--------------> FFmpeg
```

The frontend is responsible for the user interface and user interactions, while the backend handles API requests, data processing, machine learning, and audio processing.

---

## Tech Stack

### Frontend

* Laravel
* Blade
* Vite
* Tailwind CSS
* PHP

### Backend

* Python
* Flask
* FFmpeg
* Firebase

### Machine Learning

* Deep Learning
* Audio Classification
* Music Mood Classification
* Music Recommendation

---

## Screenshots

| Image 1                                                                                    |   Image 2                                                                                        |                             
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | 
| ![Image 1](https://drive.google.com/uc?id=1rFt-kM8CiWKUH6Zxvgga6YQDntFpYb9l)                  | ![Image 2](https://drive.google.com/uc?id=1rSnQCbe6P7qi3DZFT2pXlmyiRXlX14zY)                  | 
| ![Image 3](https://drive.google.com/uc?id=1KmOesukRKxKVEqcJSfI8VE7iJkLXmISK)                  | ![Image 4](https://drive.google.com/uc?id=1b8xFSd-MfFumPNkqCwyc3ZAm6zgieKJt)                  |
| ![Image 5](https://drive.google.com/uc?id=1XjFa5mKpKM-3lB2N98-L3B7Ig-QGTia8)                  | ![Image 6](https://drive.google.com/uc?id=1uS4Nj2FW0VwwX_Takh72yHVgJ8zh3nDS)                 | 
| ![Image 5](https://drive.google.com/uc?id=1f_NHgE1qK-dB7g3eGhTZgsSJ5bRpTfPu)                  | ![Image 6](https://drive.google.com/uc?id=1kZB1zNvdiwTqcpfc_NvgAqxCXd0gW_v7)                 | 
| ![Image 5](https://drive.google.com/uc?id=1SPthq60DoOXE9wIIkc98jibSaxqmtDdH)                  | ![Image 6](https://drive.google.com/uc?id=1yqKy_w--xOD5wV7wMko2DjYC1hJTwzDv)                 | 
| ![Image 5](https://drive.google.com/uc?id=1c49e5MN02dEvWvmw68Sm_jly05xA1BG0)                  |                 | 

---

## UI/UX Design

The application UI/UX was designed using Figma.

[View Deep Music Figma Design](https://www.figma.com/design/zmZ5mHpB7X5ZYcii8bYFOY/Project-Deep-Learning--Copy-?node-id=1-6016&t=n2pLmWluOG5JXFFw-1)

---

## Contributors

This project was developed as a team project.

Special thanks to all team members who contributed to the planning, design, development, testing, and documentation of this project.

* @contributor-1
* @contributor-2
* @contributor-3
* @contributor-4

---

## Areas for Improvement

This project was developed as an academic project and still has several areas that can be improved.

Potential improvements include:

* [ ] Improve model performance
* [ ] Improve music mood classification accuracy
* [ ] Develop a more advanced recommendation algorithm
* [ ] Improve code structure and maintainability
* [ ] Apply clean architecture principles
* [ ] Separate admin and user roles
* [ ] Improve API security
* [ ] Improve responsive design
* [ ] Improve UI/UX
* [ ] Add automated testing
* [ ] Add API documentation
* [ ] Apply development practices that are closer to industry standards

---

## Installation

### Prerequisites

Make sure the following tools are installed on your system:

* PHP
* Composer
* Node.js and npm
* Python
* pip
* FFmpeg
* Git

---

# Frontend Installation

### 1. Clone the Repository

```bash
git clone <REPOSITORY_URL>
cd Frontend
```

Make sure the frontend directory contains files such as:

```text
artisan
composer.json
package.json
.env.example
```

---

### 2. Install PHP Dependencies

```bash
composer install
```

---

### 3. Install Node Dependencies

```bash
npm install
```

---

### 4. Configure Environment Variables

Create a `.env` file based on `.env.example`.

For Windows PowerShell:

```powershell
Copy-Item .env.example .env
```

Then configure the environment variables according to your local setup.

Example:

```env
APP_ENV=local
APP_DEBUG=true
APP_URL=http://127.0.0.1:8080

SESSION_DRIVER=file
CACHE_STORE=file
```

Configure the API URL to point to the local Flask backend.

Example:

```env
API_BASE_URL=http://127.0.0.1:5000
```

> The environment variable name may differ depending on the API client implementation used in the project.

---

### 5. Generate the Laravel Application Key

```bash
php artisan key:generate
```

---

### 6. Run the Backend

Before running the frontend, make sure the Flask backend is running.

Navigate to the backend directory:

```bash
cd Backend
```

Create a Python virtual environment:

```bash
python -m venv venv
```

Activate the virtual environment on Windows:

```powershell
venv\Scripts\activate
```

Install the required Python dependencies:

```bash
pip install -r requirements.txt
```

Run the Flask application according to the project's entry point.

For example:

```bash
python app.py
```

The backend should then be accessible at:

```text
http://127.0.0.1:5000
```

---

### 7. Build Frontend Assets

For a production build:

```bash
npm run build
```

---

### 8. Run Laravel

Start the Laravel development server:

```bash
php artisan serve --port=8080
```

Open the application in your browser:

```text
http://127.0.0.1:8080
```

---

## Development Mode

During development, Laravel, Vite, and Flask can be run in separate terminals.

### Terminal 1 — Laravel

```bash
php artisan serve --port=8080
```

### Terminal 2 — Vite

```bash
npm run dev
```

### Terminal 3 — Flask Backend

```bash
python app.py
```

The local development architecture is:

```text
                 Browser
                    |
                    v
          +-------------------+
          | Laravel :8080     |
          | Blade Frontend     |
          +---------+---------+
                    |
                    | API Request
                    v
          +-------------------+
          | Flask :5000       |
          | Python Backend    |
          +---------+---------+
                    |
              +-----+-----+
              |           |
              v           v
          Firebase     ML Model
```

---

## Authentication Flow

Authentication is handled through communication between the Laravel frontend and the Flask backend API.

```text
User
 |
 | Login Credentials
 v
Laravel Frontend
 |
 | HTTP Request
 v
Flask API
 |
 | Authentication
 v
Authentication Result
 |
 v
Laravel Session
```

After successful authentication, Laravel stores the required user information in the session and uses it to maintain the user's authenticated state.

---

## Project Documentation

Additional project documentation and UI/UX design:

* **Figma:** [Deep Music Figma](https://www.figma.com/design/zmZ5mHpB7X5ZYcii8bYFOY/Project-Deep-Learning--Copy-?node-id=1-6016&t=n2pLmWluOG5JXFFw-1)
* **GitHub:** Add the main repository link here.

---

## Project Information

**Project Type:** Final Project — Deep Learning Course

**Project Name:** Deep Music

**Focus:**

* Music Classification
* Music Mood Classification
* Music Recommendation
* Audio Processing
* Deep Learning

---

## License

This project was created for educational purposes as part of a university course project.
