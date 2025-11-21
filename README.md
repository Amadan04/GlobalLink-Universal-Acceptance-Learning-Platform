# GlobalLink - Universal Acceptance Learning Platform

A comprehensive web application designed to educate developers and organizations about Universal Acceptance (UA) principles, Internationalized Domain Names (IDN), and Email Address Internationalization (EAI) using AI-powered tools.

## Table of Contents

- [About the Project](#about-the-project)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Folder Structure](#folder-structure)
- [API Endpoints](#api-endpoints)
- [Screenshots](#screenshots)
- [Notes & Limitations](#notes--limitations)
- [Future Improvements](#future-improvements)
- [License](#license)

## About the Project

GlobalLink is an AI-powered educational platform built to bridge the knowledge gap in Universal Acceptance (UA) standards. With the internet becoming increasingly multilingual and diverse, developers need tools and resources to build applications that properly support Internationalized Domain Names (IDNs) and Email Address Internationalization (EAI) following the IDNA2008 standard.

### Why GlobalLink?

The modern web serves billions of users speaking hundreds of languages, yet many applications still struggle with non-ASCII domain names and email addresses. This creates barriers for users whose native languages use non-Latin scripts like Arabic, Chinese, Hindi, and many others.

### Who Is It For?

- Developers looking to make their applications universally accessible
- Organizations seeking UA compliance for their systems
- Students learning about internationalization and web standards
- QA engineers testing multilingual applications

### Problem It Solves

GlobalLink addresses the critical need for UA education by providing:
- Interactive learning modules with real-world examples
- AI-powered code analysis that detects UA compliance issues
- Practical tools for testing email validation and domain linkification
- Bilingual support (English and Arabic) for broader accessibility
- Document summarization and intelligent chatbot assistance

### Main Highlights

- AI-driven code review for UA compliance using GPT-4
- RAG-based chatbot trained on official UA documentation
- Interactive learning paths (Beginner, Intermediate, Advanced)
- Real-time email and domain validation tools
- Document processing (PDF, DOCX, TXT) with OCR support for Arabic
- Progress tracking and personalized learning experience
- Newsletter subscription system with IDN email support

## Features

### Learning & Education
- Structured learning paths with three difficulty levels
- Placement quiz to assess current knowledge
- Progress tracking with scores and completion status
- Interactive lessons with practical examples

### AI-Powered Tools
- **Code Analyzer**: Analyzes code snippets for UA compliance issues and provides improvement suggestions
- **Smart Chatbot**: RAG-based assistant trained on UA documentation, answers questions in English and Arabic
- **Document Chat**: Upload documents and ask questions about their content
- **PDF Summarizer**: Generate summaries of uploaded documents in multiple languages

### Validation & Testing Tools
- Email validation supporting internationalized addresses
- Domain linkification with proper Punycode conversion
- Real-time input validation and feedback

### User Management
- Email-based authentication with verification codes
- User progress persistence across sessions
- Newsletter subscription with bilingual email templates

## Tech Stack

### Frontend
- **React** with TypeScript
- **Vite** - Fast build tool
- **React Router** - Client-side routing
- **Framer Motion** - Smooth animations
- **Tailwind CSS** - Utility-first styling
- **Axios** - HTTP client
- **Zustand** - State management
- **Prism.js** - Syntax highlighting
- **Lucide React** - Icon library

### Backend
- **Node.js** with Express.js
- **MongoDB** with Mongoose - Data persistence
- **OpenAI API** - GPT-4 for AI features
- **Nodemailer** - Email delivery
- **Multer** - File upload handling
- **Tesseract.js** - OCR for scanned documents
- **pdf-parse** & **pdf2json** - PDF text extraction
- **Mammoth** - DOCX processing
- **langdetect** - Language detection
- **bidi-js** - RTL text handling

### Standards & Libraries
- **idna-uts46** - IDNA2008 compliant domain processing
- **punycode** - Unicode/ASCII domain conversion
- **CORS** - Cross-origin resource sharing
- **dotenv** - Environment configuration

## Installation

### Prerequisites
- Node.js (v16 or higher)
- MongoDB (v4.4 or higher)
- OpenAI API key
- SMTP server credentials (for email features)

### Backend Setup

1. Navigate to the backend directory:
```bash
cd BackEnd
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file in the BackEnd directory (see [Configuration](#configuration))

4. Start the backend server:
```bash
node server.mjs
```

The backend will run on `http://localhost:3000` by default.

### Frontend Setup

1. Navigate to the frontend directory:
```bash
cd FrontEnd
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

The frontend will run on `http://localhost:5173` by default.

## Configuration

### Backend Environment Variables

Create a `.env` file in the `BackEnd` directory with the following variables:

```env
# Server Configuration
PORT=3000
HOST=localhost

# OpenAI Configuration
OPENAI_API_KEY=your_openai_api_key_here

# MongoDB Configuration
MONGO_URI=mongodb://localhost:27017/ua-platform

# Email Configuration (SMTP)
EMAIL_HOST=your_smtp_host
EMAIL_PORT=465
EMAIL_USER=your_email_username
EMAIL_PASS=your_email_password
```

### Frontend Configuration

The frontend automatically connects to `http://localhost:3000` for API calls. If your backend runs on a different port or host, update the API base URL in the frontend configuration files.

## Usage

### Running the Full Application

1. Start MongoDB service on your machine
2. Start the backend server from the `BackEnd` directory
3. Start the frontend development server from the `FrontEnd` directory
4. Open your browser and navigate to `http://localhost:5173`

### Using the Code Analyzer

1. Navigate to Tools > Code Analyzer
2. Paste your code snippet in the editor
3. Select the output language (Arabic or English)
4. Click "Analyze" to receive AI-powered feedback on UA compliance

### Using the Chatbot

1. Access the chatbot from the home page
2. Ask questions about Universal Acceptance in English or Arabic
3. Upload documents for context-aware responses
4. View conversation history for reference

### Learning Modules

1. Create an account or log in
2. Take the placement quiz to assess your level
3. Complete lessons in your recommended track
4. Track your progress on the learning dashboard

## Folder Structure

```
AI-TRA-Hackathon/
├── BackEnd/
│   ├── server.mjs                 # Main Express server
│   ├── EmailRoutes.js             # Email and authentication routes
│   ├── index.js                   # Entry point
│   ├── package.json               # Backend dependencies
│   ├── .env                       # Environment variables (not in repo)
│   ├── .gitignore                 # Git ignore rules
│   ├── embeddings.json            # Pre-computed text embeddings
│   ├── ua_cleaned_v2.txt          # UA training content
│   ├── training.txt               # Additional training data
│   ├── analyzeCodeTraining.txt    # Code analysis training data
│   ├── UA.pdf                     # UA documentation
│   ├── GPT_API.pdf                # GPT API documentation
│   ├── ara.traineddata            # Arabic OCR data
│   ├── eng.traineddata            # English OCR data
│   ├── tessdata/                  # Tesseract OCR data files
│   ├── test/                      # Test files
│   └── uploads/                   # Uploaded files directory
│
├── FrontEnd/
│   ├── src/
│   │   ├── App.tsx                # Main React component
│   │   ├── main.tsx               # React entry point
│   │   ├── index.css              # Global styles
│   │   ├── vite-env.d.ts          # Vite type definitions
│   │   ├── components/            # Reusable UI components
│   │   │   ├── layout/            # Layout components
│   │   │   ├── ui/                # UI elements
│   │   │   └── RealTimeLinkifier.tsx
│   │   ├── pages/                 # Page components
│   │   │   ├── HomePage.tsx
│   │   │   ├── AboutPage.tsx
│   │   │   ├── ToolsPage.tsx
│   │   │   ├── ResourcesPage.tsx
│   │   │   ├── LearnPage.tsx
│   │   │   ├── SubscribePage.tsx
│   │   │   ├── 404.tsx
│   │   │   ├── auth/              # Authentication pages
│   │   │   ├── learn/             # Learning module pages
│   │   │   └── tools/             # Tool pages
│   │   ├── context/               # React context providers
│   │   ├── store/                 # Zustand state management
│   │   └── utils/                 # Utility functions
│   ├── public/                    # Static assets
│   ├── package.json               # Frontend dependencies
│   ├── package-lock.json
│   ├── vite.config.ts             # Vite configuration
│   ├── tsconfig.json              # TypeScript configuration
│   ├── tsconfig.app.json
│   ├── tsconfig.node.json
│   ├── tailwind.config.js         # Tailwind CSS configuration
│   ├── postcss.config.js          # PostCSS configuration
│   ├── eslint.config.js           # ESLint configuration
│   ├── index.html                 # HTML entry point
│   ├── .gitignore
│   └── .bolt/                     # Build configuration
│
└── README.md                      # This file
```

## API Endpoints

### Chat & AI
- `POST /ask` - Ask questions to the AI chatbot
- `POST /analyze-text` - Analyze code for UA compliance
- `POST /summarize-pdf` - Generate document summaries
- `POST /upload-doc-chat` - Upload document for chat context
- `POST /ask-doc-chat` - Ask questions about uploaded document

### Email & Validation
- `POST /api/validate-email` - Validate email addresses
- `POST /api/linkify` - Convert single domain/email to link
- `POST /api/linkify-text` - Linkify all domains/emails in text
- `POST /api/subscribe` - Subscribe to newsletter
- `POST /api/sendSubscribeEmail` - Send email to all subscribers

### Authentication
- `POST /api/signup` - Create new account
- `POST /api/login` - Request login verification code
- `POST /api/verify-code` - Verify authentication code

### User Progress
- `POST /api/progress/update` - Update lesson progress
- `GET /api/progress/:email` - Get user progress
- `GET /api/users/:email` - Get user information

### File Operations
- `POST /upload` - Upload multiple files
- `GET /analyze` - Analyze uploaded files

## Screenshots

_Screenshots placeholder - Add images to showcase:_
- Home page with chatbot interface
- Code analyzer tool in action
- Learning module interface
- Email validation tool
- Progress tracking dashboard

## Notes & Limitations

### Current Limitations
- OCR functionality for scanned PDFs is commented out due to dependency complexity
- Email service requires proper SMTP server configuration
- Large PDF processing may take time depending on document size
- Embedding generation is done once at server startup and cached

### Known Issues
- Some PDF formats may not extract text correctly
- Language detection defaults to Arabic when uncertain
- File upload size is limited by server configuration

### Performance Considerations
- First-time embedding generation takes several minutes
- Subsequent API calls are fast due to pre-computed embeddings
- Document processing time scales with file size

## Future Improvements

### Planned Features
- Real-time collaboration on code analysis
- Additional language support beyond English and Arabic
- Integration with popular IDEs for inline UA checking
- Mobile application for on-the-go learning
- Gamification with badges and achievements
- Community forum for UA discussions
- Video tutorials and interactive demonstrations

### Technical Enhancements
- Implement WebSocket for real-time chat updates
- Add caching layer (Redis) for improved performance
- Implement rate limiting for API protection
- Add comprehensive test coverage
- Docker containerization for easier deployment
- CI/CD pipeline setup
- Enhanced error handling and logging
- Performance monitoring and analytics

### Content Expansion
- More comprehensive lesson library
- Real-world case studies
- Best practices guide for different frameworks
- API integration examples for popular services

## License

This project was developed for the 2025 Bahrain Hackathon.


ISC License - See repository for details.

---

Made with commitment to Universal Acceptance and digital inclusion.
