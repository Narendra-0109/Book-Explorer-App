Book Explorer Full-Stack Application
This is a full-stack web application for an online bookstore, built as an assignment to demonstrate skills in web scraping, backend API development, and a modern frontend interface.

Project Structure
The repository is organized into three main directories:

/scraper: Contains the Node.js script for scraping data.

/backend: Holds the Express.js server and API endpoints.

/frontend: Contains the React application for the user interface.

Functional Overview
The /scraper script scrapes book information (title, price, rating, etc.) from https://books.toscrape.com/.

The scraped data is stored in a MySQL database.

The /backend provides a RESTful API to access the book data, with support for searching, filtering, and pagination.

The /frontend is a React application that fetches data from the backend API and displays it in a user-friendly, responsive interface.

Getting Started
Prerequisites
Node.js (v18 or higher)

npm (Node Package Manager)

MySQL Server (v8 or higher)

MySQL Workbench (or a similar tool)

Step 1: Clone the Repository
git clone <your-repo-url>
cd "Book Explorer App"

Step 2: Database Setup
Open MySQL Workbench and create a new database named book_explorer.

Run the following SQL script to create the books table:

USE book_explorer;

CREATE TABLE books (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    price DECIMAL(10, 2) NOT NULL,
    stock_availability VARCHAR(50) NOT NULL,
    rating INT NOT NULL,
    book_detail_page_url VARCHAR(255) NOT NULL,
    thumbnail_image_url VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

Step 3: Run the Data Scraper
Navigate to the scraper directory and install dependencies:

cd scraper
npm install cheerio axios mysql2

Update the database credentials in scraper.js to match your MySQL setup.

Run the scraper script to populate the database:

node scraper.js

(Note: This may take a few moments as it scrapes all 50 pages.)

Step 4: Run the Backend API
Open a new terminal and navigate to the backend directory:

cd backend
npm install express mysql2 cors

Update the database credentials in server.js.

Start the backend server:

node server.js

The server will run on http://localhost:3001.

Step 5: Launch the Frontend
Open a third terminal and navigate to the frontend directory:

cd frontend
npm install

Launch the React application:

npm start

The app will open in your browser at http://localhost:3000.

Author: [Narendra Gurjar]
