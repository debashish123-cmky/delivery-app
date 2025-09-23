# 🍕 Delivery App

A modern, full-stack food delivery application built with React and Firebase. This app provides a seamless experience for users to browse menus, place orders, and track their delivery status.

## ✨ Features

- **🔐 User Authentication**
  - Secure email/password registration and login
  - Protected routes and user sessions
  - Password reset functionality
  - User profile management

- **🛒 Order Management**
  - Browse interactive menu with visual items
  - Add/remove items from cart
  - Real-time cart updates and price calculations
  - Order placement and tracking

- **📊 User Dashboard**
  - Order history and status tracking
  - User statistics and insights
  - Profile management

- **📱 Responsive Design**
  - Mobile-first approach
  - Modern UI with Tailwind CSS
  - Smooth animations and interactions
  - Dark/light theme support

- **🔥 Firebase Integration**
  - Real-time database with Firestore
  - Secure authentication
  - User data persistence
  - Analytics integration



## 🛠️ Tech Stack

- **Frontend:**
  - React 18
  - React Router DOM
  - Tailwind CSS
  - Lucide React (Icons)
  - Class Variance Authority

- **Backend & Services:**
  - Firebase Authentication
  - Cloud Firestore
  - Firebase Analytics
  - Firebase Hosting (for deployment)

- **Development:**
  - Create React App
  - ESLint
  - Git & GitHub

## 📋 Prerequisites

Before running this project, make sure you have:

- Node.js (v16 or higher)
- npm or yarn
- Firebase account
- Git

## 🔧 Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/debashish123-cmky/delivery-app.git
cd delivery-app
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Firebase Setup
1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Create a new project or use existing one
3. Enable Authentication → Sign-in method → Email/Password
4. Create a Firestore database
5. Add your domain to authorized domains

### 4. Environment Configuration
Create a `.env` file in the root directory (optional, for production):
```env
REACT_APP_FIREBASE_API_KEY=your_api_key
REACT_APP_FIREBASE_AUTH_DOMAIN=your_auth_domain
REACT_APP_FIREBASE_PROJECT_ID=your_project_id
REACT_APP_FIREBASE_STORAGE_BUCKET=your_storage_bucket
REACT_APP_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
REACT_APP_FIREBASE_APP_ID=your_app_id
```

### 5. Firestore Security Rules
Add these rules in Firebase Console → Firestore → Rules:
```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
    match /orders/{orderId} {
      allow read, write: if request.auth != null && request.auth.uid == resource.data.userId;
    }
  }
}
```

### 6. Start Development Server
```bash
npm start
```

The app will open at `http://localhost:3000`

## 📁 Project Structure

```
delivery-app/
├── public/
│   ├── index.html
│   └── favicon.ico
├── src/
│   ├── components/
│   │   ├── ui/                 # Reusable UI components
│   │   ├── layout/             # Layout components (Header, Footer)
│   │   └── ProtectedRoute.jsx  # Route protection
│   ├── contexts/
│   │   └── AuthContext.jsx     # Authentication context
│   ├── hooks/
│   │   └── use-toast.js        # Toast notifications hook
│   ├── pages/
│   │   ├── AuthPage.jsx        # Login/Register page
│   │   ├── PlaceOrder.jsx      # Menu and ordering
│   │   ├── Dashboard.jsx       # User dashboard
│   │   └── Profile.jsx         # User profile
│   ├── lib/
│   │   └── utils.js            # Utility functions
│   ├── firebase.js             # Firebase configuration
│   ├── App.jsx                 # Main app component
│   └── index.js                # App entry point
├── .gitignore
├── package.json
├── tailwind.config.js
└── README.md
```

## 🎯 Usage

### For Users:
1. **Register/Login**: Create an account or sign in
2. **Browse Menu**: Explore available food items
3. **Add to Cart**: Select items and quantities
4. **Place Order**: Review and confirm your order
5. **Track Status**: Monitor order progress in dashboard

### For Developers:
1. **Authentication**: Managed through Firebase Auth
2. **State Management**: React Context API
3. **Database**: Firestore for user data and orders
4. **Styling**: Tailwind CSS with custom components
5. **Routing**: Protected routes with React Router

## 🚀 Deployment

### Deploy to Firebase Hosting
```bash
# Install Firebase CLI
npm install -g firebase-tools

# Login to Firebase
firebase login

# Initialize Firebase in your project
firebase init hosting

# Build the project
npm run build

# Deploy to Firebase
firebase deploy
```

### Deploy to Netlify
1. Push your code to GitHub
2. Connect your GitHub repo to Netlify
3. Set build command: `npm run build`
4. Set publish directory: `build`
5. Deploy!

### Deploy to Vercel
```bash
# Install Vercel CLI
npm install -g vercel

# Deploy
vercel --prod
```

## 🧪 Testing

```bash
# Run tests
npm test

# Run tests with coverage
npm test -- --coverage
```

## 📈 Performance Optimizations

- **Code Splitting**: Lazy loading of route components
- **Image Optimization**: Optimized images and icons
- **Bundle Optimization**: Tree shaking and minification
- **Caching**: Service worker for offline functionality
- **Database**: Optimized Firestore queries

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Debashish**
- GitHub: [@debashish123-cmky](https://github.com/debashish123-cmky)
- Email: https://mithudeb113@gmail.com

## 🙏 Acknowledgments

- [React](https://reactjs.org/) - UI library
- [Firebase](https://firebase.google.com/) - Backend services
- [Tailwind CSS](https://tailwindcss.com/) - Styling framework
- [Lucide React](https://lucide.dev/) - Icon library
- [Create React App](https://create-react-app.dev/) - Project bootstrap

## 📞 Support

If you have any questions or need help, please:
1. Check the [Issues](https://github.com/debashish123-cmky/delivery-app/issues) page
2. Create a new issue if needed
3. Contact me directly

---

⭐ **Star this repository if you found it helpful!**

Made with ❤️ by [Debashish](https://github.com/debashish123-cmky)
