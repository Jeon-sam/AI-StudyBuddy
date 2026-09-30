AI StudyBuddy API
An AI-powered educational backend built with Node.js, Express, MongoDB, and Gemini 2.5 Flash.

Features
JWT auth stored in HTTP-only cookies (access + refresh tokens)
Role-Based Access Control (student / admin)
Upload study materials (.txt, .md, .pdf)
AI-powered: summarize, flashcards, quiz, study plan via Gemini 2.5 Flash
Setup
1. Install dependencies
npm install
2. Create .env file
PORT=5000
MONGO_URI=mongodb://localhost:27017/ai-studybuddy
JWT_ACCESS_SECRET=your_access_secret_here
JWT_REFRESH_SECRET=your_refresh_secret_here
GEMINI_API_KEY=your_gemini_api_key_here
NODE_ENV=development
3. Run the server
node index.js
Project Structure
ai-studybuddy/
├── index.js                     # Entry point
├── uploads/                     # Temp file storage
└── src/
    ├── controllers/
    │   ├── authController.js    # register, login, refresh, logout
    │   ├── materialController.js# upload + all AI features
    │   └── adminController.js   # admin-only routes
    ├── middleware/
    │   ├── auth.js              # protect + adminOnly
    │   └── upload.js            # multer config
    ├── models/
    │   ├── User.js
    │   └── Material.js
    ├── routes/
    │   ├── auth.js
    │   ├── materials.js
    │   └── admin.js
    └── utils/
        ├── db.js                # MongoDB connection
        ├── gemini.js            # Gemini AI helper
        └── tokens.js            # JWT + cookie helpers
