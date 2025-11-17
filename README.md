# Miles & Memories – A Personal Travel Journal for Wanderers

## 1. Project Title  
**Miles & Memories – A Personal Travel Journal for Wanderers**

## 2. Problem Statement  
In the age of social media, travelers often find it difficult to maintain a personal, organized, and meaningful record of their journeys.  
While platforms like Instagram or blogs allow sharing experiences, they lack privacy, structure, and efficient searchability.

Many travelers want a dedicated space where they can document trips with photos, stories, and dates — accessible anytime, anywhere.  
Miles & Memories solves this by providing a personal travel journal platform that allows users to record, edit, and relive their travel stories with images, dates, and filters — all under secure authentication.

Users can pin favorite trips, search by date, and manage stories effortlessly in a visually appealing, responsive interface.  
The system is also optimized with pagination, ensuring fast performance even with large collections of stories.

---

## 3. System Architecture

### **Architecture Flow:**  
**Frontend → Backend (API) → Database**

### **Frontend:**
- Built with React.js (web) using Hooks (useState, useEffect, useContext)
- Axios / Fetch for API communication
- Pagination-ready UI, supporting “Load More” or Infinite Scroll
- Responsive design using modern CSS (Flexbox, Grid)

### **Backend:**
- Node.js + Express.js for REST API development
- Multer for handling image uploads
- JWT for secure authentication
- Pagination using query parameters with Mongoose `.skip()` and `.limit()`
- CORS & bcrypt.js for security and password hashing

### **Database:**
- MongoDB Atlas – Cloud-based NoSQL database for users and stories
- Collections: `users`, `stories`

### **Authentication:**
- JWT-based login/signup with secure tokens
- Roles: Basic user only

### **Hosting / Infrastructure:**
- **Frontend:** Vercel / Netlify  
- **Backend:** Render / AWS EC2  
- **Database:** MongoDB Atlas

### **Additional Modules:**
- Image Upload & Storage Service (via Multer)
- Search & Filter Service (by date range)
- Pinned Stories Service (favorite stories)
- Pagination Module (limit and skip results for scalable story browsing)

---

## 4. Key Features

| Category                | Features |
|------------------------|----------|
| Authentication & Security | Secure JWT-based authentication; User signup, login, and logout |
| CRUD Operations | Add, edit, and delete personal travel stories (title, description, image, date) |
| Image Upload | Upload and preview travel images using Multer |
| Date & Filtering | Attach travel dates and search/filter stories by date range |
| Favorites | Pin favorite stories to the top of the feed |
| Pagination | Efficient story loading with pagination (page and limit-based APIs) |
| Responsive Design | Fully responsive UI with smooth transitions and modern animations |
| Frontend Interaction | Real-time updates, form validation, and “Load More” pagination using React hooks |
| Error Handling | Frontend error messages and backend validation with clear HTTP responses |
| Hosting & Deployment | Fully deployed frontend and backend with live MongoDB Atlas connection |

---

## 5. Tech Stack

| Layer | Technologies |
|-------|--------------|
| Frontend | React.js, Axios, HTML, CSS (responsive UI), useState/useEffect/useContext |
| Backend | Node.js, Express.js, Multer |
| Database | MongoDB Atlas |
| Authentication | JWT (JSON Web Tokens), bcrypt.js |
| Pagination Logic | Mongoose `.skip()` and `.limit()` with query parameters |
| Hosting / Infrastructure | Vercel (Frontend), Render / AWS (Backend) |
| Other Tools | Postman (API testing), GitHub (version control) |

---

## 6. API Overview

| Endpoint | Method | Description | Access |
|----------|--------|-------------|--------|
| /api/auth/signup | POST | Register a new user | Public |
| /api/auth/login | POST | Authenticate user and issue JWT token | Public |
| /api/stories | GET | Fetch all stories (supports pagination via ?page & limit) | Authenticated |
| /api/stories/:id | GET | Fetch specific story by ID | Authenticated |
| /api/stories | POST | Create a new story (text, image, date) | Authenticated |
| /api/stories/:id | PUT | Edit an existing story | Authenticated |
| /api/stories/:id | DELETE | Delete a story | Authenticated |
| /api/stories/search?startDate=&endDate= | GET | Search/filter stories by date range | Authenticated |
| /api/stories/pin/:id | PATCH | Pin or unpin a story as favorite | Authenticated |
| /api/upload | POST | Upload images using Multer | Authenticated |
| /api/users/profile | GET / PUT | View or update user profile | Authenticated |

---

