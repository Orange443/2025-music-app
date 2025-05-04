# 2025 music app
Music Streaming App (Tunes Library)
# Music Streaming App (Tunes Library)

A Flask-based web application for streaming music, managing albums and songs, user roles (User, Creator, Admin), playlists, ratings, and more.

**Deployed Version:** [ADI443.pythonanywhere.com](http://ADI443.pythonanywhere.com)

## Features

* User Registration and Login (User, Creator, Admin roles)
* Music playback
* Album and Song management (CRUD operations for Creators)
* Playlist creation for users
* Song rating (Like/Dislike)
* Admin dashboard with app statistics and song charts
* Admin features: Song flagging, Creator review (Blacklist/Whitelist)
* Search functionality

## Technologies Used

* **Backend:** Python, Flask, Flask-SQLAlchemy
* **Database:** SQLite (default, configurable via environment variable)
* **Frontend:** HTML, CSS, Bootstrap, Jinja2, JavaScript (for Chart.js)
* **Environment Management:** python-dotenv

## Local Setup and Installation

Follow these steps to run the application on your local machine.

**Prerequisites:**

* Python 3.x installed
* Git installed

**Steps:**

1.  **Clone the repository (or download the code):**
    ```bash
    git clone <your-github-repository-url>
    cd Music-Streaming-App-MAD---I
    ```
    *(Replace `<your-github-repository-url>` with the actual URL)*

2.  **Create and activate a virtual environment:**
    * On macOS/Linux:
        ```bash
        python3 -m venv venv
        source venv/bin/activate
        ```
    * On Windows:
        ```bash
        python -m venv venv
        .\venv\Scripts\activate
        ```

3.  **Install the required dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Create environment variables:**
    Create a file named `.env` in the root directory (`Music-Streaming-App-MAD---I/`) and add the following lines. Replace the placeholders with your actual values.
    ```dotenv
    # Example .env file
    SQLALCHEMY_DATABASE_URI='sqlite:///tuneslibrary.db' # Use 'sqlite:///' followed by your desired DB name
    SQLALCHEMY_TRACK_MODIFICATIONS=False
    SECRET_KEY='replace_with_a_very_strong_random_secret_key' # Generate a strong secret key
    ```
    * **Important:** The `.gitignore` file should already include `.env` to prevent committing this file.

5.  **Initialize the Database and Create Uploads Folder:**
    The application should create the SQLite database file (`tuneslibrary.db` or whatever you named it in `.env`) automatically when first run, based on the `models.py` setup. Also, create the folder for song uploads if it doesn't exist:
    ```bash
    mkdir uploads
    ```
    *(The app needs this folder to save uploaded MP3 files).*

6.  **Run the Flask application:**
    ```bash
    flask run
    ```
    *(Or `python app.py` if `flask run` gives issues)*

7.  **Access the application:**
    Open your web browser and navigate to `http://127.0.0.1:5000` (or the address provided in the terminal). You should see the login page.

    * **Default Admin Login:** Username: `admin`, Password: `admin` (as defined in `models.py`)

## Project Structure
