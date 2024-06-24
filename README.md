World Traveler API

## Overview

This Express.js application provides a simple API to track your visited countries. Users can view a list of visited countries on the homepage and add new ones through a form.

## Features

View a list of visited countries
Add new countries to your list
Error handling for invalid country names and duplicate entries

## Installation

Clone this repository:

git clone https://your-repository-url.git
Install dependencies:

npm install
This installs express, body-parser, and pg (for PostgreSQL connection).

## Configuration

### Database Connection

This application assumes a PostgreSQL database named worlds with a table named countries containing country codes and names, and a table named visited_countries to store visited country codes. You can modify the db configuration in index.js to match your database setup:

JavaScript
const db = new pg.Client({
user: "postgres",
host: "localhost",
database: "worlds",
password: "your_database_password",
port: 5432,
});
Use code with caution.
content_copy

## Running the Application

Start the server:

npm start
Access the application in your browser at http://localhost:3000.

## Usage

Home Page (GET /):
Displays a list of visited countries retrieved from the database.
Add Country (POST /add):
Submits a form with a country name.
The API checks if the country exists in the countries table.
If found, it adds the corresponding country code to the visited_countries table and redirects to the home page with an updated list.
If not found or an error occurs, it displays an error message on the home page.

## API Reference

GET /:
Returns a list of visited countries (JSON format).

## Development

Feel free to modify the code to add more features, such as:

Country details (e.g., name, flag)
User authentication
Additional error handling
Unit tests

## License

This project is licensed under the MIT License (see LICENSE.md for details).

## Contributing

We welcome contributions to improve this project! Please create a pull request to share your changes.
