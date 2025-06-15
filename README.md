# 📝 Blog Platform – Full Stack Project

## 📌 Project Overview

A comprehensive full-stack blog publishing platform that allows users to create, read, update, and delete blog posts. The platform includes features like user authentication, blog interaction (likes, comments, bookmarks), image uploads, and responsive design for both web and mobile interfaces.

### Key Features

- � User authentication (register, login, logout)
- ✍️ Create, edit, and delete blog posts
- 📸 Upload images for blog posts
- ❤️ Like/unlike blogs
- 🔖 Bookmark blogs for later reading
- 💬 Comment on blog posts
- 👁️ Track blog views
- 🏷️ Add tags to categorize blogs
- 📱 Responsive web and mobile interfaces

## 🔧 Tech Stack

| Component | Technology |
|-----------|------------|
| Frontend  | React, Redux Toolkit, SCSS |
| Backend   | Node.js, Express, Firebase (Firestore) |
| Mobile    | Flutter, GetX state management |
| Database  | Firebase Firestore |
| Authentication | Firebase Auth |
| Storage   | Base64 encoding (images) |

## 🚀 Setup Instructions

### Prerequisites

- Node.js (v14 or higher)
- npm or yarn
- Flutter SDK (for mobile app)
- Firebase account

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a Firebase project and download the service account key:
   - Go to Firebase Console (https://console.firebase.google.com/)
   - Create a new project or use an existing one
   - Go to Project Settings > Service Accounts
   - Generate a new private key and save it as `firebase-adminsdk.json` in the backend directory

4. Start the server:
   ```bash
   npm start
   ```
   The server will run on http://localhost:5000

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm start
   ```
   The frontend will run on http://localhost:3000

### Mobile App Setup

1. Navigate to the mobile directory:
   ```bash
   cd mobile
   ```

2. Install Flutter dependencies:
   ```bash
   flutter pub get
   ```

3. Run the app:
   ```bash
   flutter run
   ```

## 📱 Mobile App Features

The Flutter mobile app includes:

- User authentication
- View all blogs
- View user's own blogs
- Create new blogs
- Like and bookmark blogs
- Comment on blogs
- View blog details
- Edit and delete user's own blogs

## 🤖 AI Tools and Prompting Techniques Used

Throughout the development of this project, I leveraged various AI tools to enhance productivity and solve complex problems:

### Tools Used

1. **ChatGPT (GPT-4)**: Used for code generation, debugging, and architecture planning
2. **GitHub Copilot**: Used for code completion and suggestions during development
3. **Midjourney**: Used for generating placeholder images and design inspiration

### Prompting Techniques

1. **Chain-of-Thought Prompting**: 
   - Used to break down complex problems into smaller, manageable steps
   - Example: When implementing the authentication flow, I asked the AI to outline each step from user input to token storage

2. **Role-Based Prompting**:
   - Assigned specific roles to the AI (e.g., "Act as a Flutter expert")
   - Example: When designing the mobile UI, I asked the AI to act as a UI/UX designer to suggest improvements

3. **Iterative Refinement**:
   - Started with a basic implementation and iteratively improved it
   - Example: For the blog detail screen, I began with a simple layout and gradually enhanced it with features like comments and likes

4. **Code Debugging**:
   - Provided error messages and code snippets for the AI to analyze
   - Example: When facing issues with Firebase authentication, I shared the error logs for the AI to suggest solutions

### Specific Use Cases

1. **Backend Development**:
   - Used AI to generate boilerplate code for Express routes and controllers
   - Implemented Firebase Firestore integration with AI assistance
   - Debugged authentication middleware with AI suggestions

2. **Frontend Development**:
   - Generated Redux slice templates for blogs and authentication
   - Implemented responsive design patterns with AI guidance
   - Created form validation logic with AI assistance

3. **Mobile Development**:
   - Designed Flutter UI components with AI suggestions
   - Implemented state management using GetX with AI guidance
   - Created reusable widgets for blog cards and comments

4. **Cross-Platform Integration**:
   - Ensured consistent API interactions between web and mobile apps
   - Standardized data models across platforms

### Challenges Faced

1. **Firebase Integration**:
   - Challenge: Complex security rules and authentication flow
   - Solution: Used AI to generate and explain Firebase security rules and authentication patterns

2. **State Management**:
   - Challenge: Managing global state across multiple components
   - Solution: AI helped implement Redux for web and GetX for mobile with proper patterns

3. **Image Handling**:
   - Challenge: Efficiently storing and retrieving images
   - Solution: AI suggested using Base64 encoding for simplicity in this project

4. **Mobile-Web Consistency**:
   - Challenge: Maintaining consistent user experience across platforms
   - Solution: AI helped design shared data models and API interaction patterns

## � API Documentation

### Authentication Endpoints

- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login a user
- `GET /api/auth/user` - Get current user info

### Blog Endpoints

- `GET /api/blogs` - Get all blogs
- `GET /api/blogs/:id` - Get a specific blog
- `POST /api/blogs` - Create a new blog
- `PUT /api/blogs/:id` - Update a blog
- `DELETE /api/blogs/:id` - Delete a blog
- `POST /api/blogs/:id/like` - Like a blog
- `POST /api/blogs/:id/unlike` - Unlike a blog
- `POST /api/blogs/:id/view` - Increment blog view count

### User Endpoints

- `GET /api/users/blogs` - Get blogs by current user
- `POST /api/users/bookmark/:id` - Bookmark a blog
- `DELETE /api/users/bookmark/:id` - Remove a bookmark
- `GET /api/users/bookmarks` - Get all bookmarked blogs

## 📋 Project Structure

```
blog-platform/
├── backend/               # Node.js Express backend
│   ├── config/            # Configuration files
│   ├── controllers/       # Request handlers
│   ├── middleware/        # Express middleware
│   ├── models/            # Data models
│   ├── routes/            # API routes
│   └── server.js          # Entry point
├── frontend/              # React frontend
│   ├── public/            # Static files
│   └── src/               # Source files
│       ├── app/           # Redux store setup
│       ├── components/    # Reusable components
│       ├── features/      # Redux slices
│       ├── pages/         # Page components
│       └── services/      # API services
└── mobile/                # Flutter mobile app
    ├── android/           # Android-specific files
    ├── ios/               # iOS-specific files
    └── lib/               # Dart source files
        ├── controllers/   # GetX controllers
        ├── models/        # Data models
        ├── services/      # API services
        └── views/         # UI screens
```

## 🔮 Future Enhancements

- Real-time notifications for likes and comments
- Advanced search and filtering
- User profiles with avatars
- Social sharing integration
- Rich text editor for blog creation

## 📜 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

Developed with ❤️ using React, Node.js, Firebase, and Flutter