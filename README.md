# 🗳️ PollSystem - Advanced Polling Platform

## 🌟 Overview

PollSystem is a comprehensive polling and voting platform that enables secure, democratic decision-making through modern web technologies. Built with a focus on security, user experience, and scalability, it offers both public polling capabilities and advanced administrative tools.

### ✨ Key Highlights

- 🤖 **AI-Powered Poll Creation** - Generate polls using natural language with Groq AI
- 🔐 **Secure Email-Based Voting** - Token-based authentication prevents duplicate voting
- 📊 **Real-Time Results** - Live updating charts and analytics
- 👨‍💼 **Advanced Admin Dashboard** - Comprehensive poll management and voter audit trails
- 📱 **Responsive Design** - Beautiful UI with Tailwind CSS and Shadcn/UI components
- 🎨 **Interactive Visualizations** - Multiple chart types with Recharts
- ⚡ **High Performance** - Fast loading with Vite and optimized backend

---

## 🚀 Features

### 🗳️ Core Polling Features
- **Poll Creation & Management** - Create polls with 2-10 customizable options
- **Smart Token System** - Email-based voting tokens with expiration and security
- **Vote Validation** - Prevents duplicate voting and ensures data integrity
- **Flexible Settings** - Configure email requirements, result visibility, and multiple votes
- **Poll Status Control** - Activate/deactivate polls dynamically

### 🤖 AI Integration
- **Natural Language Poll Generation** - Describe your poll idea, let AI create the structure
- **Intelligent Option Suggestions** - AI generates relevant and balanced poll options
- **Context-Aware Creation** - Understands poll requirements and creates appropriate options

### 📊 Analytics & Visualization
- **Real-Time Results** - Live updating poll results with WebSocket-like polling
- **Multiple Chart Types** - Bar charts, pie charts, and donut charts
- **Voter Analytics** - Track voter participation and engagement
- **Export Capabilities** - Download results and voter data

### 🛡️ Security & Authentication
- **Admin Secret Protection** - Secure admin access with configurable secrets
- **Rate Limiting** - Prevents spam and abuse (3 token requests/hour per IP)
- **Token Encryption** - Secure token hashing and validation
- **Audit Trails** - Complete voting history with IP and timestamp tracking

### 🎨 User Experience
- **Modern UI/UX** - Clean, intuitive interface with smooth animations
- **Dark/Light Mode Support** - Automatic theme detection and switching
- **Mobile Responsive** - Optimized for all device sizes
- **Toast Notifications** - Real-time feedback for user actions
- **Loading States** - Smooth loading indicators and skeleton screens

---

## 🏗️ Architecture

### Frontend Stack
- **React 18** - Modern React with hooks and functional components
- **Vite** - Lightning-fast build tool and development server
- **Tailwind CSS** - Utility-first CSS framework
- **Shadcn/UI** - High-quality component library
- **Framer Motion** - Smooth animations and transitions
- **Recharts** - Beautiful and responsive charts
- **React Router** - Client-side routing and navigation
- **Axios** - HTTP client for API communication

### Backend Stack
- **Node.js & Express** - RESTful API server
- **MongoDB & Mongoose** - Document database with ODM
- **Groq SDK** - AI integration for intelligent poll creation
- **Nodemailer** - Email service for voting tokens
- **bcrypt** - Password hashing and encryption
- **express-rate-limit** - API rate limiting middleware
- **CORS** - Cross-origin resource sharing configuration

---

## 📁 Project Structure

```
webwizards/
├── 📁 frontend/
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   │   ├── ui/         # Shadcn/UI components
│   │   │   ├── charts/     # Chart components
│   │   │   └── layout/     # Layout components
│   │   ├── pages/          # Route components
│   │   ├── services/       # API services
│   │   ├── hooks/          # Custom React hooks
│   │   ├── lib/            # Utility functions
│   │   └── utils/          # Helper functions
│   ├── public/             # Static assets
│   └── index.html          # Entry HTML file
├── 📁 backend/
│   ├── models/             # MongoDB schemas
│   ├── routes/             # API route handlers
│   ├── middleware/         # Express middleware
│   ├── services/           # Business logic services
│   ├── utils/              # Utility functions
│   └── server.js           # Express server entry
└── 📄 README.md            # Project documentation
```

---

## 🛠️ Installation & Setup

### Prerequisites
- Node.js 18+ and npm/yarn
- MongoDB Atlas account or local MongoDB instance
- Groq API key for AI features (optional)
- SMTP email service for voting tokens

### 1. Clone the Repository
```bash
git clone https://github.com/nandit27/Web-Wizards2025.git
cd Web-Wizards2025
```

### 2. Backend Setup
```bash
cd backend
npm install

# Create environment file
cp .env.example .env
```

Configure your `.env` file:
```env
# Database
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/pollsystem

# Server Configuration
PORT=3001
NODE_ENV=development
FRONTEND_URL=http://localhost:3000

# Admin Configuration
ADMIN_SECRET=your-super-secure-admin-secret

# Email Configuration (for voting tokens)
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your-email@gmail.com
EMAIL_PASS=your-app-password

# AI Configuration (Optional - for AI poll generation)
VITE_LLM_API_KEY=your-groq-api-key
VITE_LLM_MODEL=llama-3.3-70b-versatile
```

### 3. Frontend Setup
```bash
cd ../
npm install

# Create environment file
cp .env.example .env.local
```

Configure your frontend `.env.local`:
```env
VITE_API_URL=http://localhost:3001/api
VITE_LLM_API_KEY=your-groq-api-key
```

### 4. Start Development Servers
```bash
# Terminal 1 - Backend
cd backend
npm run dev

# Terminal 2 - Frontend
cd ../
npm run dev
```

Visit `http://localhost:3000` to access the application!

---

## 📖 Usage Guide

### 🎯 For Poll Creators (Public)

1. **View Available Polls** - Browse all active polls on the homepage
2. **Request Voting Token** - Enter your email to receive a secure voting link
3. **Cast Your Vote** - Click the magic link in your email to vote
4. **View Results** - See real-time results with beautiful charts

### 👨‍💼 For Administrators

1. **Access Admin Dashboard** - Visit `/admin` and enter your admin secret
2. **Create Polls** - Use the manual form or AI-powered generation
3. **Manage Polls** - Activate/deactivate, edit, or delete polls
4. **Monitor Voting** - View voter audit trails and detailed analytics
5. **Export Data** - Download results and voter information

### 🤖 AI Poll Creation

1. Navigate to Admin Dashboard
2. Click "Create with AI"
3. Describe your poll in natural language:
   - "Create a poll about favorite programming languages"
   - "Survey about remote work preferences with 5 options"
   - "Poll for choosing the next team building activity"
4. AI generates title, description, and relevant options
5. Review and customize before publishing

---

## 🔌 API Documentation

### Public Endpoints
- `GET /api/polls` - List all active polls
- `GET /api/polls/:id` - Get poll details
- `POST /api/request-token` - Request voting token
- `POST /api/polls/:id/vote` - Cast vote with token
- `GET /api/polls/:id/results` - Get poll results

### Admin Endpoints (Require `X-Admin-Secret` header)
- `POST /api/admin/polls` - Create new poll
- `GET /api/admin/polls` - List all polls with admin data
- `GET /api/admin/polls/:id/audit` - Get voting audit trail
- `PUT /api/admin/polls/:id` - Update poll
- `DELETE /api/admin/polls/:id` - Delete poll

### Rate Limits
- Token requests: 3 per hour per IP address
- General API: 100 requests per 15 minutes per IP

---

## 🎨 Screenshots

<div align="center">

### 🏠 Home Page - Poll Listing
<img width="1710" height="795" alt="Screenshot 2025-09-27 at 4 07 30 PM" src="https://github.com/user-attachments/assets/6dc01b62-c254-45e9-8952-f52d7d28613e" />


### 🗳️ Voting Interface
<img width="1710" height="985" alt="Screenshot 2025-09-27 at 4 08 17 PM" src="https://github.com/user-attachments/assets/f90ee661-aa03-4f47-963c-e65eb4e69e28" />


### 📊 Results Dashboard
<img width="1432" height="520" alt="Screenshot 2025-09-27 at 4 09 23 PM" src="https://github.com/user-attachments/assets/bb1e82b7-3360-4efe-b3d0-9e0fe0ce8fb7" />


### 👨‍💼 Admin Dashboard
<img width="1710" height="933" alt="Screenshot 2025-09-27 at 4 10 00 PM" src="https://github.com/user-attachments/assets/b2691a74-fb63-4867-993f-a4a9a20a1086" />


</div>

---

## 🚦 Use Cases

### 🏢 Business & Organizations
- **Team Decision Making** - Choose project directions, meeting times, or office policies
- **Product Development** - Gather user feedback on features and priorities
- **Event Planning** - Select venues, dates, or activity preferences
- **HR Surveys** - Anonymous employee satisfaction and feedback collection

### 🎓 Education
- **Classroom Polls** - Interactive learning and student engagement
- **Course Evaluation** - Gather student feedback on curriculum
- **Student Elections** - Secure voting for student government
- **Research Surveys** - Academic research data collection

### 🏛️ Community & Government
- **Community Decisions** - Neighborhood improvements and local initiatives
- **Budget Allocation** - Public input on spending priorities
- **Policy Feedback** - Citizen input on proposed regulations
- **Event Organization** - Community event planning and coordination

### 🎉 Personal & Social
- **Event Planning** - Party themes, restaurant choices, vacation destinations
- **Group Activities** - Movie nights, game selection, outing plans
- **Gift Selection** - Collaborative gift choosing for special occasions
- **Opinion Surveys** - Gather thoughts from friends and family

---

## 🤝 Contributing

We welcome contributions! Here's how you can help:

### 🐛 Bug Reports
1. Check existing issues first
2. Create detailed bug reports with:
   - Steps to reproduce
   - Expected vs actual behavior
   - Screenshots if applicable
   - Environment details

### ✨ Feature Requests
1. Search existing feature requests
2. Provide detailed descriptions with:
   - Use case and benefits
   - Proposed implementation
   - Mockups or examples

### 💻 Code Contributions
1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Make your changes with tests
4. Commit with descriptive messages
5. Push to your branch
6. Open a Pull Request

### 📝 Development Guidelines
- Follow existing code style and conventions
- Write tests for new features
- Update documentation as needed
- Ensure all tests pass before submitting

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- **Shadcn/UI** - For the beautiful component library
- **Groq** - For AI-powered poll generation capabilities
- **Recharts** - For stunning data visualizations
- **Framer Motion** - For smooth animations
- **Tailwind CSS** - For rapid UI development
- **MongoDB Atlas** - For reliable database hosting

---

## 📞 Support & Contact

- 📧 Email: [your-email@example.com](mailto:your-email@example.com)
- 🐛 Issues: [GitHub Issues](https://github.com/nandit27/Web-Wizards2025/issues)
- 💬 Discussions: [GitHub Discussions](https://github.com/nandit27/Web-Wizards2025/discussions)
- 📖 Docs: [Documentation](https://your-docs-url.com)

---

<div align="center">

**Made with ❤️ by the Web Wizards Team**

⭐ **Star this repo if you find it helpful!** ⭐

[⬆️ Back to Top](#-pollsystem---advanced-polling-platform)

</div>
