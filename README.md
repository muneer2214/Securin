Recipe Catalog Application
This is a single-page React application that serves as a dynamic and interactive recipe catalog. It simulates a full-stack environment by using a mock API layer to handle data fetching, pagination, and filtering. The application provides users with a clean, responsive interface to browse, search, and view detailed information about various recipes.

Features
Responsive Recipe Table: Displays a paginated list of recipes with key information.

Dynamic Filtering: Users can filter the recipes by title, cuisine, rating, total_time, and serves directly from the table headers.

Pagination: The application supports navigation through large datasets with "Previous" and "Next" buttons, as well as a dropdown to adjust the number of items per page.

Detailed Recipe View: Clicking on any recipe row opens a detailed view in a slide-out drawer, showing ingredients, instructions, nutritional information, and more.

Simulated Backend: The application includes a mock api layer that mimics a real RESTful API, complete with functions for pagination, sorting, and filtering.

Star Ratings: Visual star ratings are displayed for each recipe, providing a quick overview of its quality.

Error and Loading States: The UI provides clear feedback to the user when data is loading or when no search results are found.

Getting Started
This application is built as a single, self-contained React component (App.js) and can be run directly in any environment that supports a modern React setup.

Prerequisites:

Node.js and npm (or yarn) installed on your machine.

Installation:

Copy the entire code block into a new file named App.js.

Set up a basic React project. For example, using Create React App:

npx create-react-app recipe-catalog-app
cd recipe-catalog-app

Replace the contents of src/App.js with the provided code.

Remove the default src/App.css and src/index.css files, or clear their contents.

Install Tailwind CSS for styling:

npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p

Configure your tailwind.config.js to include the project's files:

/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}

Add the Tailwind directives to your src/index.css file:

@tailwind base;
@tailwind components;
@tailwind utilities;

Run the development server:

npm start

Project Structure
data: The rawRecipes array at the top of the file acts as the in-memory database.

api: A JavaScript object containing functions that simulate API calls (getRecipes, searchRecipes).

App component: The main React component that handles the UI, state management, and data fetching logic.

StarRating component: A helper component for displaying ratings.

Implementation Details
The core of the application lies in its state management and a single useEffect hook that efficiently handles both pagination and filtering.

When a user applies a filter, the hasFilters state becomes true, triggering a call to the api.searchRecipes function.

When no filters are active, the application defaults back to using api.getRecipes for paginated browsing.

This approach ensures the application remains performant and responsive, regardless of the user's interaction.
