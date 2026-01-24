# Quiz Application

A modern, interactive quiz application built with React that allows users to take quizzes on various topics, track their progress, and view detailed performance reports.

## Features

### Authentication System
- **User Registration**: Create a new account with username, email, and password
- **User Login**: Secure login with validation
- **Session Management**: Persistent login state using localStorage
- **Protected Routes**: Quiz access restricted to authenticated users only

###  Quiz Management
- **10 Diverse Quizzes**: Covering topics like JavaScript, React, HTML/CSS, Python, General Knowledge, Web Development, Database Concepts, Computer Science, Git, and Node.js
- **Multiple Questions**: Each quiz contains multiple questions with 4 options each
- **Navigation Controls**: Easy navigation between quizzes with Previous/Next buttons
- **Progress Tracking**: Visual indicator showing current quiz position (e.g., "Quiz 1 of 10")

###  Interactive Quiz Experience
- **Answer Selection**: Click-to-select answer options with visual feedback
- **Answer Persistence**: Selected answers are saved when navigating between quizzes
- **Real-time Updates**: Instant visual feedback for selected options
- **Question Details**: Each question displays its point value

###  Comprehensive Reporting
- **Score Calculation**: Automatic calculation of total marks and percentage
- **Grade System**: Letter grades (A+, A, B+, B, C, F) based on performance
- **Detailed Breakdown**: 
  - Quiz-wise performance analysis
  - Question-by-question results
  - Correct/Incorrect/Unanswered indicators
  - Marks obtained per question
- **Answer Review**: View selected answers vs correct answers for wrong questions
- **Statistics**: Total questions, correct answers, wrong answers, and unanswered questions

###  User Interface
- **Modern Design**: Clean, responsive UI with smooth animations
- **Color-Coded Results**: Visual indicators for correct (green), incorrect (red), and unanswered (gray) questions
- **Mobile Responsive**: Optimized for all screen sizes
- **Intuitive Navigation**: Easy-to-use interface with clear visual hierarchy

##  Tech Stack

- **Frontend Framework**: React 19.2.0
- **Routing**: React Router DOM 7.12.0
- **Build Tool**: Vite 7.2.4
- **Styling**: CSS Modules
- **Language**: JavaScript (ES6+)

##  Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v16 or higher)
- **npm** or **yarn** package manager

##  Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd quizapp
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start the development server**
   ```bash
   npm run dev
   ```

4. **Open your browser**
   Navigate to `http://localhost:5173` (or the port shown in your terminal)

##  Usage

### Getting Started

1. **Register a New Account**
   - Navigate to the Register page
   - Fill in your username, email, and password
   - Confirm your password
   - Click "Register" to create your account

2. **Login**
   - Go to the Login page
   - Enter your username and password
   - Click "Login" to access the quiz

3. **Take a Quiz**
   - Once logged in, you'll see the quiz interface
   - Navigate through quizzes using Previous/Next buttons
   - Click on an option to select your answer
   - Selected answers are automatically saved
   - On the last quiz, click "Submit Quiz" to complete

4. **View Results**
   - After submission, view your detailed score report
   - Review your performance quiz-by-quiz
   - See which questions you got right or wrong
   - Click "Retake Quiz" to start over

##  Project Structure

```
quizapp/
├── public/
│   └── vite.svg
├── src/
│   ├── auth/
│   │   ├── Login.jsx              # Login component
│   │   ├── Login.module.css       # Login styles
│   │   ├── Register.jsx            # Registration component
│   │   └── Register.module.css    # Registration styles
│   ├── components/
│   │   ├── CustomeButton.jsx       # Reusable button component
│   │   ├── CustomeButton.module.css
│   │   ├── QuizBox.jsx             # Quiz display component
│   │   ├── QuizBox.module.css      # Quiz styles
│   │   ├── ReportCard.jsx          # Results display component
│   │   └── ReportCard.module.css   # Report card styles
│   ├── data/
│   │   └── quizes.js               # Quiz data (10 quizzes)
│   ├── pages/
│   │   ├── Home.jsx                # Main quiz page
│   │   └── Home.module.css         # Home page styles
│   ├── App.jsx                     # Main app component with routing
│   ├── main.jsx                    # Entry point
│   ├── index.css                   # Global styles
│   └── App.css                     # App styles
├── index.html
├── package.json
├── vite.config.js
├── netlify.toml              # Netlify deployment configuration
└── README.md
```

##  Quiz Topics

The application includes 10 comprehensive quizzes:

1. **JavaScript Fundamentals** - Core JavaScript concepts
2. **React Basics** - React library fundamentals
3. **HTML & CSS** - Web markup and styling
4. **Python Programming** - Python language basics
5. **General Knowledge** - Trivia and general information
6. **Web Development** - Web technologies and APIs
7. **Database Concepts** - SQL and database fundamentals
8. **Computer Science Basics** - Algorithms and data structures
9. **Git & Version Control** - Version control with Git
10. **Node.js & Backend** - Server-side JavaScript

##  Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint

##  Deployment

This application is configured for deployment on Netlify. The necessary configuration files are already included in the project.

### Netlify Deployment

#### Option 1: Deploy via Netlify Dashboard

1. **Build the project locally** (optional, for testing):
   ```bash
   npm run build
   ```

2. **Push your code to GitHub**:
   ```bash
   git add .
   git commit -m "Ready for deployment"
   git push origin main
   ```

3. **Deploy on Netlify**:
   - Go to [Netlify](https://www.netlify.com/)
   - Sign up or log in
   - Click "Add new site" → "Import an existing project"
   - Connect to your GitHub repository
   - Netlify will automatically detect the build settings from `netlify.toml`:
     - **Build command**: `npm run build`
     - **Publish directory**: `dist`
   - Click "Deploy site"

4. **Configure custom domain** (optional):
   - Go to Site settings → Domain management
   - Add your custom domain

#### Option 2: Deploy via Netlify CLI

1. **Install Netlify CLI**:
   ```bash
   npm install -g netlify-cli
   ```

2. **Login to Netlify**:
   ```bash
   netlify login
   ```

3. **Initialize and deploy**:
   ```bash
   netlify init
   netlify deploy --prod
   ```

### Build Configuration

The project includes:
- **`netlify.toml`**: Netlify configuration file with build settings
- **`public/_redirects`**: SPA routing configuration for React Router

### Important Notes

- The build output directory is `dist` (Vite default)
- All routes are redirected to `index.html` for client-side routing
- Node.js version is set to 18 in the build environment
- The application uses localStorage, so data persists per browser/device

### Testing Production Build Locally

Before deploying, test the production build locally:

```bash
npm run build
npm run preview
```

Visit `http://localhost:4173` to preview the production build.

##  Features in Detail

### Authentication Flow
- Users must register before accessing quizzes
- Login credentials are validated against stored user data
- Session persists across page refreshes
- Logout functionality clears session data

### Quiz Navigation
- Navigate between 10 different quizzes
- Previous button disabled on first quiz
- Next button disabled on last quiz
- Quiz counter shows current position

### Answer Management
- Select answers by clicking on options
- Visual feedback with radio button indicators
- Answers persist when switching between quizzes
- All answers tracked until quiz submission

### Scoring System
- Each question has assigned marks
- Automatic calculation of total and obtained marks
- Percentage-based scoring
- Letter grade assignment based on performance

##  Future Enhancements

Potential features for future versions:
- Timer for each quiz
- Quiz categories and filtering
- User profile and quiz history
- Leaderboard system
- Quiz creation/editing interface
- Export results as PDF
- Dark mode theme

##  Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

##  License

This project is open source and available under the [MIT License](LICENSE).

## 👤 Author

Created with ❤️ for learning and assessment purposes.

## 🙏 Acknowledgments

- React team for the amazing framework
- Vite for the fast build tool
- All contributors and testers

---

**Note**: This application uses localStorage for data persistence. User data and quiz results are stored locally in the browser.

