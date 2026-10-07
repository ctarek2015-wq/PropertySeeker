<p align="center">
  <img src="./public/logo/logo.jpeg" alt="PropertySeeker logo" width="600">
</p>

# PropertySeeker

PropertySeeker is a real estate marketplace for buying or renting homes in Bahrain. Seekers can filter listings, inspect property images, book viewing appointments and leave property reviews. Owners manage listings, images and viewing availability.

Built by [Ahmed Tarek](https://github.com/ctarek2015-wq).

[Open the deployed PropertySeeker app](https://propertyseeker.onrender.com/)

## Implemented Features

- Owner and seeker registration with role-specific workflows.
- Sale/rent listings with price, location, bedrooms, bathrooms and area.
- Filters for price, area, bedrooms, bathrooms, location, rating and availability.
- Cloudinary image uploads, removal and main-image selection.
- Viewing availability, appointment booking and appointment management.
- Property reviews and ratings.
- Profile management, welcome/appointment emails and password-reset emails.

## Stack and Architecture

JavaScript, Node.js, Express 5, EJS, MongoDB/Mongoose, Cloudinary/Multer, Express Session/Connect Mongo, bcryptjs and Nodemailer.

`server.js` configures Express, server-rendered EJS views, MongoDB-backed sessions and routers. Controllers coordinate the user, property, availability, viewing and review models. Multer reads uploads in memory; Cloudinary stores property media. Nodemailer services use Gmail for email delivery.

## Local Setup

Use Node.js 20.20.2 (recorded in `.node-version`), a MongoDB database, Cloudinary credentials and a Gmail app password for email features.

```bash
git clone https://github.com/ctarek2015-wq/PropertySeeker.git
cd PropertySeeker
npm install
```

Create a local `.env` file with your own values:

```env
MONGODB_URI=your_mongodb_connection_string
SESSION_SECRET=your_long_random_session_secret
EMAIL_USER=your_gmail_address
EMAIL_APP_PASSWORD=your_gmail_app_password
CLOUDINARY_URL=cloudinary://your_api_key:your_api_secret@your_cloud_name
PORT=3000
NODE_ENV=development
```

```bash
npm run dev
```

Open `http://localhost:3000`. `npm start` runs the server without Nodemon. Production uses `NODE_ENV=production` with HTTPS so secure session cookies work.

## Seed Mock Properties

Point `MONGODB_URI` at a development database, then run:

```bash
npm run seed:mockdata
```

The script creates fifteen properties with four remote images each, five Bahraini owners and viewing availability. The mock owners use `MockOwner123!`; their emails are listed in [mockdata/properties.js](./mockdata/properties.js). Use this data only for development demonstrations.

## Screenshots

<table>
  <tr>
    <td><img src="./public/screenShots/homepage.png" alt="PropertySeeker home page"></td>
    <td><img src="./public/screenShots/newproppage.png" alt="New property page"></td>
  </tr>
  <tr>
    <td><img src="./public/screenShots/profilepage.png" alt="PropertySeeker profile page"></td>
    <td><img src="./public/screenShots/signuppage.png" alt="PropertySeeker sign-up page"></td>
  </tr>
</table>

## Planning Materials

- [Role-specific dashboard wireframes](./public/wireframe/roles-dashboards.png)
- [Property detail wireframe](./public/wireframe/property-page.png)
- [Search results wireframe](./public/wireframe/search-results.png)
- [Navigation wireframe](./public/wireframe/global-navbar.png)
- [Database entity relationship diagram](./public/erd/ERD.png)

## Current Limits and Next Steps

Listing pagination and a dedicated floorplan-upload workflow are not implemented. `npm test` is a placeholder; there is no committed automated test suite. Cloudinary and Gmail features require working credentials. Future improvements include workflow onboarding, loading feedback and regression coverage.

## Attributions

- [Google Fonts](https://fonts.google.com/) provides the Manrope and Space Grotesk typefaces.
- [Unsplash](https://unsplash.com/) provides the remote mock property images; image rights remain subject to the photographers' terms.
- [Cloudinary](https://cloudinary.com/) hosts uploaded images.
