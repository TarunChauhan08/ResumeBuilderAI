# 📄 Resume Builder - Full Stack Application

A modern, feature-rich resume builder application built with React and Node.js. Create professional resumes with AI-powered enhancements, multiple templates, and real-time preview.

## ✨ Features

### Core Features
- **Multiple Resume Templates**: Choose from Classic, Modern, Minimal, and Minimal Image templates
- **Real-Time Preview**: See your changes instantly as you build your resume
- **AI-Powered Enhancements**: 
  - Enhance professional summaries with AI
  - Improve job descriptions with AI suggestions
  - Upload and extract data from existing PDF resumes
- **Customizable Design**: 
  - Custom accent colors
  - Multiple professional templates
  - Background removal for profile images
- **User Authentication**: Secure user registration and login system
- **Resume Management**: 
  - Create multiple resumes
  - Save and edit resumes
  - Public/Private resume sharing
  - Download resumes as PDF
- **Profile Image Upload**: Upload and manage profile pictures with ImageKit integration

### Additional Features
- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- **Dashboard**: Manage all your resumes from a centralized dashboard
- **Share Functionality**: Share public resumes with a simple link
- **Print/Download**: Export your resume as PDF using browser print functionality

## 🛠️ Tech Stack

### Frontend
- **React 19** - UI library
- **Vite** - Build tool and dev server
- **Redux Toolkit** - State management
- **React Router DOM** - Routing
- **Tailwind CSS** - Styling
- **Lucide React** - Icons
- **Axios** - HTTP client
- **React Hot Toast** - Notifications
- **React PDF to Text** - PDF parsing

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database (via Mongoose)
- **JWT** - Authentication
- **Bcrypt** - Password hashing
- **Multer** - File upload handling
- **ImageKit** - Image storage and CDN
- **OpenAI API** - AI-powered resume enhancements

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v18 or higher)
- **npm** or **yarn**
- **MongoDB** (local installation or MongoDB Atlas account)
- **Git**

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd resume-builder
   ```

2. **Install client dependencies**
   ```bash
   cd client
   npm install
   ```

3. **Install server dependencies**
   ```bash
   cd ../server
   npm install
   ```

## ⚙️ Environment Variables

### Server Environment Variables

Create a `.env` file in the `server` directory with the following variables:

```env
# Server Configuration
PORT=3000

# MongoDB Connection
MONGODB_URI=mongodb://localhost:27017
# OR for MongoDB Atlas:
# MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net

# JWT Secret
JWT_SECRET=your_jwt_secret_key_here

# OpenAI Configuration
OPENAI_API_KEY=your_openai_api_key_here
OPENAI_MODEL=gpt-3.5-turbo
# OR
# OPENAI_MODEL=gpt-4

# ImageKit Configuration
IMAGEKIT_PUBLIC_KEY=your_imagekit_public_key
IMAGEKIT_PRIVATE_KEY=your_imagekit_private_key
IMAGEKIT_URL_ENDPOINT=your_imagekit_url_endpoint
```

### Client Environment Variables

Create a `.env` file in the `client` directory:

```env
VITE_API_URL=http://localhost:3000
```

## 🏃 Running the Application

### Development Mode

1. **Start the MongoDB server** (if using local MongoDB)
   ```bash
   mongod
   ```

2. **Start the backend server**
   ```bash
   cd server
   npm run server
   ```
   The server will run on `http://localhost:3000`

3. **Start the frontend development server** (in a new terminal)
   ```bash
   cd client
   npm run dev
   ```
   The client will run on `http://localhost:5173` (or another port if 5173 is busy)

### Production Build

1. **Build the frontend**
   ```bash
   cd client
   npm run build
   ```

2. **Start the production server**
   ```bash
   cd server
   npm start
   ```

## 📁 Project Structure

```
resume-builder/
├── client/                 # Frontend React application
│   ├── src/
│   │   ├── app/           # Redux store and slices
│   │   ├── assets/        # Static assets and templates
│   │   ├── components/    # React components
│   │   │   ├── home/     # Home page components
│   │   │   └── templates/ # Resume templates
│   │   ├── configs/       # API configuration
│   │   ├── pages/         # Page components
│   │   └── main.jsx       # Entry point
│   ├── public/            # Public assets
│   └── package.json
│
├── server/                # Backend Node.js application
│   ├── configs/          # Configuration files
│   │   ├── ai.js         # OpenAI configuration
│   │   ├── db.js         # MongoDB connection
│   │   ├── imageKit.js   # ImageKit configuration
│   │   └── multer.js     # File upload configuration
│   ├── controllers/      # Route controllers
│   │   ├── aiController.js
│   │   ├── resumeController.js
│   │   └── userController.js
│   ├── middlewares/      # Express middlewares
│   │   └── authMiddleware.js
│   ├── models/           # MongoDB models
│   │   ├── Resume.js
│   │   └── User.js
│   ├── routes/           # API routes
│   │   ├── aiRoutes.js
│   │   ├── resumeRoutes.js
│   │   └── userRoutes.js
│   ├── server.js         # Server entry point
│   └── package.json
│
└── README.md
```

## 🔌 API Endpoints

### Authentication Routes (`/api/users`)
- `POST /api/users/register` - Register a new user
- `POST /api/users/login` - Login user
- `GET /api/users/data` - Get current user data (protected)

### Resume Routes (`/api/resumes`)
- `GET /api/resumes/get/:resumeId` - Get a specific resume (protected)
- `GET /api/resumes/all` - Get all user's resumes (protected)
- `POST /api/resumes/create` - Create a new resume (protected)
- `PUT /api/resumes/update` - Update a resume (protected)
- `DELETE /api/resumes/delete` - Delete a resume (protected)
- `GET /api/resumes/public/:resumeId` - Get public resume (public)

### AI Routes (`/api/ai`)
- `POST /api/ai/enhance-pro-sum` - Enhance professional summary (protected)
- `POST /api/ai/enhance-job-desc` - Enhance job description (protected)
- `POST /api/ai/upload-resume` - Extract data from PDF resume (protected)

## 💻 Usage

1. **Register/Login**: Create an account or login to access the dashboard
2. **Create Resume**: Click "Create New Resume" from the dashboard
3. **Fill Information**: 
   - Personal Information (name, email, phone, location, etc.)
   - Professional Summary (use AI enhancement for better results)
   - Work Experience (add multiple positions)
   - Education (add degrees and certifications)
   - Projects (showcase your projects)
   - Skills (list your technical and soft skills)
4. **Customize**: 
   - Choose from available templates
   - Select accent color
   - Upload profile picture
5. **Save & Share**: 
   - Save your resume
   - Make it public to share with a link
   - Download as PDF

## 🎨 Available Templates

1. **Classic Template** - Traditional, professional layout
2. **Modern Template** - Contemporary design with clean lines
3. **Minimal Template** - Simple and elegant
4. **Minimal Image Template** - Minimal design with profile image

## 🔒 Security Features

- Password hashing with bcrypt
- JWT-based authentication
- Protected API routes
- CORS configuration
- Input validation

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the ISC License.

## 🙏 Acknowledgments

- OpenAI for AI-powered enhancements
- ImageKit for image storage and CDN
- All the open-source libraries that made this project possible

## 📧 Support

For support, email your-email@example.com or create an issue in the repository.

---

**Made with ❤️ using React and Node.js**
