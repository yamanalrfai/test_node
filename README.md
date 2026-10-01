# Expense Tracker

A full-stack web application built to track personal expenses, allowing users to log, categorize, and monitor their spending. Developed as the final project for the Dalil Training Academy Full Stack Web Development program, it features a responsive UI, a robust Express API, and seamless PostgreSQL integration.

## How to run

**Database**
1. Open pgAdmin and create a new database named `expense_tracker`.
2. Open the Query Tool for the new database, paste the contents of `backend/schema.sql`, and execute it to create the `expenses` table and seed the initial data.

**Backend**
1. Navigate into the `backend` folder in your terminal.
2. Duplicate the `.env.example` file, rename it to `.env`, and fill in your PostgreSQL database credentials (specifically `DB_PASSWORD`).
3. Run `npm install` to install all necessary dependencies (Express, pg, cors, dotenv).
4. Run `npm start` (or `node server.js`) to start the server on `http://localhost:3000`.

**Frontend**
1. Navigate to the `frontend` folder in VS Code.
2. Right-click `index.html` and select **"Open with Live Server"** to launch the application in your browser. 
*(Note: Ensure any active browser VPN extensions are temporarily disabled, as they can block the frontend from communicating with the local backend).*

## Features

- [x] Add an expense (with validation)
- [x] Delete an expense
- [x] Edit an expense
- [x] Filter by category
- [x] Summary cards (total, count, highest)
- [x] Data is saved in a PostgreSQL database
- [x] **Bonus:** Export expenses to a downloadable CSV file

## Screenshots
in ./screenshoot

## What was the hardest part?

The most challenging part of the project was managing data formats and keeping the UI perfectly synced with the data objects. For example, PostgreSQL sends dates as full ISO timestamps (2026-02-06T21:00:00.000Z), which broke the HTML <input type="date"> fields in the edit modal until I used .split('T')[0] to extract just the readable date. Additionally, I had to rewrite the logic for the summary cards. Initially, finding the highest expense threw away the expense name and left a placeholder "N/A" on the screen. By refactoring the code to use .reduce(), I was able to isolate the entire expense object, allowing me to display both the highest amount and its matching title dynamically.

## The record 
[my recording](https://drive.google.com/file/d/1egR2hZTQtXecSbp_7oteVoHgZ4OwrFfg/view?usp=drive_link)