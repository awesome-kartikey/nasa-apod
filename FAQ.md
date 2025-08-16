# Frequently Asked Questions (FAQ)

### Q1: Why does the app use `DEMO_KEY` for the NASA API? Are there limitations?

**A:** The `DEMO_KEY` is provided by NASA for easy testing and demonstration purposes without requiring users to register for a personal key immediately. However, it has strict rate limits (requests per hour). For regular use or development, it's highly recommended to obtain a free personal API key from [NASA APIs](https://api.nasa.gov/) and replace `'DEMO_KEY'` in `script.js`.

### Q2: How are my favorite images stored?

**A:** Your favorite images are stored directly in your web browser's `localStorage`. This is a simple client-side storage mechanism.

### Q3: What happens if I clear my browser's cache or `localStorage`?

**A:** Since favorites are stored in `localStorage`, clearing your browser's data (specifically `localStorage` for this site) will permanently delete your saved favorites list. There is no server-side backup in this application.

### Q4: Why does the app only load 10 images at a time when I click "Load More"?

**A:** The number of images fetched per request is determined by the `count` variable set in `script.js` (currently `const count = 10;`). This value is passed to the NASA APOD API. This is done to manage the amount of data fetched at once and improve perceived performance. You could modify this variable to load more or fewer images per request, keeping API limits in mind.

### Q5: Can I view the APOD image for a specific date?

**A:** This feature is not currently implemented in the application. The NASA APOD API supports fetching images by date, but the current `script.js` only fetches a random count of recent images. Adding date-specific fetching would require modifying the API call logic.

### Q6: Is the application responsive? Will it work on mobile?

**A:** Yes, the application includes basic CSS media queries (`@media screen and (max-width: 800px)`) in `style.css` to adjust the layout for smaller screens like tablets and smartphones. The image container width adjusts, and text sizes/line heights are slightly modified.

### Q7: How is the infinite scrolling or "Load More" functionality implemented?

**A:** It's not technically infinite scrolling but a "Load More" button. When the "Load More" button is clicked (`onclick="getNasaPictures()"`), the `getNasaPictures` function is called again. This function fetches a new batch of images from the NASA API and updates the DOM to display them using the `updateDOM('results')` function, effectively replacing the previous set.

### Q8: What data is fetched for each image?

**A:** For each image, the application fetches and potentially uses the following data provided by the NASA APOD API: `url` (standard image URL), `hdurl` (high-definition image URL), `title`, `explanation`, `date`, and `copyright`.

### Q9: What happens if the NASA API call fails?

**A:**     The current implementation has a basic `try...catch` block around the `fetch` call in `getNasaPictures`. However, the `catch` block is empty. In a production scenario, this should be improved to display a user-friendly error message (e.g., "Failed to load images, please try again later.") and potentially log the error for debugging.
