# MERN Portfolio

A full-stack personal portfolio website built with the MERN stack (MongoDB-ready, Express, React, Node.js). The backend serves a React production build and exposes a contact-form API that sends emails via SendGrid.

**Live Demo:** [https://mern-portfolio-7-7opt.onrender.com](https://mern-portfolio-7-7opt.onrender.com)

## Features

- React frontend (served as a static production build by Express)
- Contact form backend with email delivery via Nodemailer + SendGrid
- Single Express server handling both static assets and API routes
- Deployed on Render

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React (production build served via Express static middleware) |
| Backend | Node.js, Express |
| Email | Nodemailer, Nodemailer SendGrid Transport |
| Config | dotenv |
| Hosting | Render |

## Project Structure

```
Mern-Portfolio/
├── client/
│   └── build/              # React production build (served statically)
├── controllers/
│   └── portfolioController.js   # Contact form email logic
├── routes/
│   └── portfolioRoute.js        # API route definitions
├── server.js                # Express app entry point
├── package.json
└── README.md
```

## API Reference

### Send Contact Email

```
POST /api/v1/portfolio/sendEmail
```

**Request Body**

| Field | Type | Required |
|---|---|---|
| `name` | string | Yes |
| `email` | string | Yes |
| `msg` | string | Yes |

**Success Response** — `200 OK`
```json
{
  "success": true,
  "message": "Your Message Send Successfully"
}
```

**Error Response** — `500 Internal Server Error`
```json
{
  "success": false,
  "message": "Please Provide All Fields"
}
```

## Environment Variables

Create a `.env` file in the project root with the following:

```env
PORT=8080
API_SENDGRID=your_sendgrid_api_key
```

## Getting Started

### Prerequisites

- Node.js installed
- A SendGrid account and API key (for the contact form to send emails)

### Installation

```bash
# Clone the repository
git clone https://github.com/saquib4292/Mern-Portfolio.git
cd Mern-Portfolio

# Install dependencies
npm install

# Set up environment variables (see above)

# frontend: cd client: npm start
# backend: node server.js
```

The app will be available at `http://localhost:8080` (or the port set in `.env`).

> Note: The `client/build` folder contains the pre-built React frontend, which is served directly by the Express server. To rebuild the frontend from source, you'll need the original React source files and run `npm run build` inside the client directory.

## Deployment

This project is deployed on [Render](https://render.com). Render runs `npm install` followed by `npm start`, with `server.js` as the entry point. Make sure environment variables (`PORT`, `API_SENDGRID`) are configured in the Render dashboard.

## Author

**Md Saquib**

## License 

**MIT**

## License

This project is licensed under the MIT License.
