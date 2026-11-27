# 🎬 StudioSpace — Creative Spaces Marketplace

**Discover. Create. Collaborate.**

StudioSpace is a peer-to-peer marketplace designed to connect creative professionals with inspiring workspaces. Whether you're a photographer, filmmaker, podcaster, musician, or content creator, StudioSpace makes it easier to discover, explore, and manage creative studios and production spaces.

Find the perfect space for your next project or list your own studio and connect with creators.

## ✨ Key Features

- **Explore Creative Spaces:** Browse photo studios, film stages, podcast rooms, music suites, and workshops.
- **Search & Filter:** Find studios based on categories and available information.
- **Authentication:** Register and sign in using email/password or configured social authentication providers.
- **Studio Management:** Create, edit, view, and manage your own studio listings.
- **Admin Management:** A designated administrator can manage all studio listings.
- **Studio Booking:** Submit booking requests with a preferred date, start time, and duration.
- **Booking Dashboard:** Manage your studio booking requests from your account.
- **Booking Validation:** Prevent overlapping booking requests for the same studio and time.
- **Image Upload:** Upload studio images using ImgBB integration.
- **Responsive Design:** Enjoy a consistent experience across desktop, tablet, and mobile devices.
- **Custom UI:** Branded loading screens, custom not-found pages, and interactive animations.

## 🛠️ Technology Stack

### Frontend

- Next.js (App Router)
- React
- TypeScript
- Tailwind CSS
- GSAP
- Swiper
- React Hot Toast

### Backend

- Node.js
- Express.js
- MongoDB
- Better Auth
- JOSE (JWT verification)

### Authentication & Services

- Better Auth with MongoDB Adapter
- Better Auth JWT Plugin
- Google OAuth
- GitHub OAuth
- ImgBB Image Hosting
- Vercel Deployment

## 🏗️ Project Architecture

```text
StudioSpace/
│
├── Frontend/
│   ├── app/
│   ├── components/
│   ├── lib/
│   ├── public/
│   ├── package.json
│   └── .env
│
└── Backend/
    ├── index.js
    ├── package.json
    └── .env
```

*The folder structure above represents the general architecture. Actual directories may differ.*

## 🚀 Local Installation & Setup

Follow these steps to run StudioSpace locally.

### Prerequisites

Make sure you have installed:

- Node.js
- npm
- MongoDB database
- Git

### 1. Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd StudioSpace
```

### 2. Install Frontend Dependencies

```bash
npm install
```

### 3. Configure Frontend Environment Variables

Create a `.env` file in the frontend root directory.

```env
MONGODB_URI=your_auth_mongodb_connection_string

BETTER_AUTH_SECRET=use_a_long_random_secret
BETTER_AUTH_URL=http://localhost:3000
BETTER_AUTH_TRUSTED_ORIGINS=http://localhost:3000

GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret

GITHUB_CLIENT_ID=your_github_client_id
GITHUB_CLIENT_SECRET=your_github_client_secret

NEXT_PUBLIC_APP_API_URL=http://localhost:5000
NEXT_PUBLIC_STUDIO_ADMIN_EMAIL=admin@example.com

NEXT_PUBLIC_IMGBB_API_KEY=your_imgbb_api_key
```

**Important Configuration Notes:**

- `NEXT_PUBLIC_STUDIO_ADMIN_EMAIL` controls admin-related frontend UI.
- The backend must use the same administrator email through `STUDIO_ADMIN_EMAIL`.
- ImgBB uploads are performed directly from the browser, so the API key is publicly exposed. Configure appropriate account limits.
- Use a strong, unique `BETTER_AUTH_SECRET`.
- For production, configure the canonical HTTPS frontend URL in `BETTER_AUTH_URL` and add custom frontend origins to `BETTER_AUTH_TRUSTED_ORIGINS` where required.

### 4. Configure Backend Environment Variables

Navigate to your backend directory (`assingment-8 backend`) and create a `.env` file.

```env
MONGODB_URI=your_studio_mongodb_connection_string

CLIENT_URL=http://localhost:3000
BETTER_AUTH_URL=http://localhost:3000

STUDIO_ADMIN_EMAIL=admin@example.com

PORT=5000
```

### 5. Start the Backend Server

Open a terminal inside the backend directory.

```bash
npm install
npm run dev
```

The backend API will run at:

```text
http://localhost:5000
```

### 6. Start the Frontend Application

Open another terminal in the frontend directory.

```bash
npm run dev
```

### 7. Open the Application

Visit:

**http://localhost:3000**

You're ready to explore StudioSpace!

## 🌐 Deployment

### Live Application

**Frontend:** Add your deployed frontend URL.

**Backend API:**

https://assingment-8-backend-qejgfz7zd.vercel.app

The backend is deployed on Vercel, while the frontend communicates with the API through the configured `NEXT_PUBLIC_APP_API_URL`.

Make sure all production environment variables are configured correctly in your deployment settings.

## 📦 Database Structure

StudioSpace uses MongoDB to manage authentication, studio listings, and booking requests.

| Collection | Purpose |
|---|---|
| `user` / Auth collections | Authentication and user information |
| `studios` | Creative studio listings |
| `bookings` | Customer booking requests |

### Booking Management

- Every booking is associated with an authenticated customer and a studio.
- New booking requests start with `Pending` status.
- Customers can cancel their own pending booking requests.
- Overlapping booking requests for the same studio and time are rejected by the backend.

### Data Migration

The backend supports legacy studio data migration.

When the `studios` collection is empty, existing documents are copied from the legacy `Assingment` collection. The original collection remains untouched.

## 🔐 Security & Access Control

- Authentication through Better Auth.
- JWT verification using JOSE.
- Protected backend operations.
- Owner-based studio management.
- Administrator-level listing management.
- Customer-specific booking access.
- Environment-based configuration for sensitive credentials.

## 🧪 Validation

Run the following commands from the frontend directory to check the project.

**Lint:**

```bash
npm run lint
```

**Production Build:**

```bash
npm run build
```

## 👨‍💻 Author

**Mohammad Omar Faruk**

Full-Stack Web Developer | MERN Stack | Next.js

- GitHub: [MohamadOmarFaruk](https://github.com/MohamadOmarFaruk)

## ⭐ Support the Project

If you like StudioSpace, consider giving this repository a **Star ⭐** on GitHub.

Your support motivates further development and improvements!

---

<p align="center">
  **Built with ❤️ for the Creative Community.**
</p>
