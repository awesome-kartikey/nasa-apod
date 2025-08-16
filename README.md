# Awesome NASA APOD Viewer

A simple web application that fetches and displays NASA's Astronomy Picture of the Day (APOD) using the NASA API. Users can browse images, view details, and save their favorite pictures to view later.

## Features

- **Fetch NASA APOD:** Retrieves the latest pictures from NASA's APOD API.
- **Infinite Scroll (Load More):** Load more images on demand.
- **View Image Details:** See the title, full description, date, and copyright information for each image.
- **HD Image Link:** Click on an image to view the high-definition version.
- **Favorites Management:** Add images to a persistent Favorites list.
- **View Favorites:** Browse through saved favorite images.
- **Remove Favorites:** Remove images from the Favorites list.
- **Loading Indicator:** Shows a loading animation while fetching images.
- **Responsive Design:** Basic responsiveness for different screen sizes.

## Tech Stack

- **HTML:** Structure and content markup.
- **CSS:** Styling, layout (Flexbox), and basic responsiveness.
- **JavaScript (Vanilla):** Core application logic, API interaction, DOM manipulation, event handling.
- **NASA APOD API:** Source of the astronomical images and data.
- **Browser localStorage:** Client-side storage for persisting user favorites.

## Setup Instructions

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/awesome-kartikey/nasa-apod.git
    cd nasa-apod
    ```
2.  **Open the application:**
    Simply open the `index.html` file in your web browser.

3.  **(Optional) Get a NASA API Key:**
    The project uses NASA's `DEMO_KEY` by default, which has hourly rate limits. For more extensive use, it's recommended to get your own free API key from [NASA APIs](https://api.nasa.gov/) and replace `'DEMO_KEY'` in `script.js` with your key:
    ```javascript
    // In script.js
    const apiKey = "YOUR_API_KEY_HERE"; // Replace DEMO_KEY
    ```

## Usage

1.  **Loading Images:** When the page loads, it automatically fetches and displays the 10 most recent APOD images available via the API.
2.  **Load More:** Click the "Load More" button in the navigation bar to fetch and display another set of 10 images.
3.  **View HD Image:** Click on any image thumbnail to open the high-definition version in a new tab.
4.  **Add to Favorites:** Click the "Add To Favorites" text below an image description to save it. A confirmation message "ADDED!" will appear briefly.
5.  **View Favorites:** Click the "Favorites" link in the navigation bar to view all your saved images.
6.  **Remove from Favorites:** While viewing your favorites, click the "Remove Favorite" text below an image description to remove it from your list.
7.  **Return to Loading:** While viewing favorites, click the "Load More NASA Images" link to go back to the main view and fetch new images.
