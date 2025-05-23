# UniVentures

**UniVentures** is a full-stack web application that helps college students discover and share local experiences tied to their university. By integrating real-time data from the Google Places API with community-submitted content, the platform allows users to explore what’s around campus, rate and review locations, and contribute their own adventures.


## Features

- **University-Based Search**  
  Search any U.S. university by name. Campus information is automatically matched using OpenStreetMap and school domain data.

- **Public Adventures**  
  Discover real-world nearby locations using Google Places API, including restaurants, activities, stores, and more.

- **Community Adventures**  
  Users can submit custom adventures with a title, description, image, location, and category. All content is tied to a specific university.

- **Account System**  
  - Signup with `.edu` email (email verification required)  
  - Strong password enforcement  
  - Session-based authentication  
  - View and manage submitted reviews

- **Filtering and Ratings**  
  Filter adventures by type or minimum star rating. Submit 1–5 star ratings and text reviews for any location.

- **Contact Form**  
  Includes a contact page for user inquiries, routed to the UniVentures support email.

## Screenshots


### Homepage  
Searched "Missouri" in the search bar, bringing up schools that begin with that name.
![Homepage](./screenshots/homepage.png)
*Caption: Screenshot showing the homepage with the search results for universities starting with "Missouri."*


### Create an Account  
Sign up using your `.edu` email to join your university's community.  
![Create Account](./screenshots/create_account.png)
*Caption: Screenshot of the account creation page, displaying an error message when a non-**.edu** email address is entered.*

### Account Dashboard  
View your personal information, school affiliation, and all reviews you've submitted.  
![Your Account](./screenshots/your_account.png)
*Caption: Screenshot of the account dashboard, showing user information, university, reviews, and account options.*


### Example Adventure  
A user-submitted community adventure titled **"Abandoned Graffiti Tunnels"**, featuring a custom photo, description, location, a 1-5 star rating, and user reviews.  
![Example Adventure](./screenshots/example_adventure.png)
*Caption: Screenshot of a user-submitted adventure titled "Abandoned Graffiti Tunnels," with a photo, description, rating system, and user reviews.*

### University Page  
View public and community-submitted adventures with filters by rating and type.
![University Page](./screenshots/university_page2.png)
*Caption: Screenshot of the university page, showing public adventures fetched from Google Places API with filter options.*

## Tech Stack

**Frontend**
- React
- Tailwind CSS

**Backend**
- Python (Flask)
- MySQL
- Flask-Mail
- Google Places API
- OpenStreetMap API (Nominatim)

## Database Overview

UniVentures uses two MySQL databases:

- `users`: stores user account credentials and metadata  
- `schools`: stores university listings, locations, ratings, and reviews

Each user is associated with a school via email domain. University geolocation data is retrieved using OpenStreetMap, and all adventures (public or submitted) are connected to a specific campus.

## Environment Variables

To run this project locally or in a development environment, create a `.env` file using the structure below.

```env
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_mysql_password
DB_SCHOOLS=schools
DB_USERS=users

SECRET_KEY=your_flask_secret_key
SERIALIZER_SECRET=your_serializer_secret_key
ADMIN_SECRET_KEY=your_admin_key

MAIL_USERNAME=your_email@gmail.com
MAIL_PASSWORD=your_email_app_password

GOOGLE_API_KEY=your_google_maps_api_key


*To run this project locally or in deployment, the frontend expects:

REACT_APP_API_URL=https://your-backend-url.com*
```

## Hosting Notes

This project can be deployed using any combination of static frontend hosting (such as Vercel), a Python-compatible backend service (such as Railway), and a cloud-hosted MySQL provider. Before deployment, update all environment variables with production credentials.

## Project Info

This was a final project developed for a Missouri State Software Engineering course in collaboration with three other team members. Their names have been omitted here for anonymity. 

I have continued development on this project by extending its functionality and transitioning it from a local development environment to a live deployment using Vercel and Railway.

## License

This project is licensed under the [MIT License](LICENSE).
