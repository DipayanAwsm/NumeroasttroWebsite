# Numerro Astro Website

A comprehensive Docker-based numerology and astrology website with admin management, payment gateway, and video consultation booking.

## Features

- **Numerological Details**: Information about numerology services
- **Contact Page**: Contact form and information
- **Testimonials & Reviews**: User testimonials with admin approval system
- **Product Catalog**: Numerology products with details
- **Admin Dashboard**: Manage content, approve testimonials, view bookings
- **Payment Gateway**: Stripe integration for product purchases
- **Video Consultation Booking**: Book video calls with consultants
- **Email Notifications**: Notifications for bookings to admin, customer, and consultant

## Tech Stack

- **Frontend**: Next.js 14 (React)
- **Backend**: Node.js + Express
- **Database**: PostgreSQL
- **Payment**: Stripe
- **Containerization**: Docker & Docker Compose

## Setup Instructions

1. **Clone the repository** (if applicable)

2. **Set up environment variables**:
   - Create a `.env` file in the root directory with:
     ```
     STRIPE_SECRET_KEY=your_stripe_secret_key
     STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
     EMAIL_HOST=smtp.gmail.com
     EMAIL_PORT=587
     EMAIL_USER=your-email@gmail.com
     EMAIL_PASS=your-app-password
     ```

3. **Build and run with Docker**:
   ```bash
   docker-compose up --build
   ```

4. **Access the application**:
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000

5. **Create admin user**:
   - First, register a user through the frontend
   - Then update the user role to 'admin' in the database:
     ```sql
     UPDATE users SET role = 'admin' WHERE email = 'your-email@example.com';
     ```

## Default Admin Credentials

After creating your admin user, you can log in through the admin page.

## Development

- Backend runs on port 5000
- Frontend runs on port 3000
- Database runs on port 5432

## Production Deployment

1. Update environment variables for production
2. Change JWT_SECRET to a strong random string
3. Update Stripe keys to production keys
4. Configure email service credentials
5. Run `docker-compose up -d` for detached mode

