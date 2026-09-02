# AI-Powered Career Prep & Resume Analyzer

A full-stack GenAI-powered web application that analyzes a user's resume against a target job description, identifies context-aware skill gaps, and generates a personalized interview preparation roadmap — powered by the Google Gemini API.


##  Overview

Traditional resume screening tools rely on rigid keyword matching, which often misses genuine skill overlaps or exaggerates gaps. This project uses a Large Language Model (Google Gemini) to perform **context-aware** comparison between a candidate's resume and a job description — going beyond keywords to understand actual competency alignment.

The system returns a structured, hallucination-free JSON response containing:
- Overall resume-to-JD match score
- Matching vs. missing skills
- A personalized preparation roadmap
- Dynamically generated technical and behavioral interview questions

##  Key Features

- **Context-Aware Skill Gap Analysis** — goes beyond keyword matching by using LLM-based semantic comparison between resume and JD content
- **Structured, Reliable AI Output** — enforces strict JSON schema on Gemini API responses to prevent hallucinated or inconsistent output, ensuring safe integration with the backend
- **Secure Authentication** — JWT-based auth with protected routes and session handling
- **Real-Time Dashboard** — React.js interface showing match scores, skill breakdowns, and tailored interview questions
- **Persistent User Data** — MongoDB/Mongoose schemas store user profiles and historical analysis results

##  Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | React.js |
| **Backend** | Node.js, Express.js |
| **Database** | MongoDB, Mongoose |
| **Authentication** | JWT (JSON Web Tokens) |
| **AI Engine** | Google Gemini API |

##  System Architecture

```
User → React Frontend (Upload Resume + JD)
        ↓
   Express REST API (Auth, Routing, File Handling)
        ↓
   Gemini API (Structured JSON Analysis)
        ↓
   MongoDB (Store Results) → Dashboard (Display Results)
```

##  Getting Started

### Prerequisites
- Node.js (v18+)
- MongoDB (local or Atlas)
- A Google Gemini API key

### Installation

```bash
# Clone the repository
git clone https://github.com/<your-username>/gemini-resume-matcher.git
cd gemini-resume-matcher

# Install backend dependencies
cd backend
npm install

# Install frontend dependencies
cd ../frontend
npm install
```

### Environment Variables

Create a `.env` file in the `backend` directory:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
GEMINI_API_KEY=your_gemini_api_key
```

### Running the App

```bash
# Start backend
cd backend
npm run dev

# Start frontend (in a new terminal)
cd frontend
npm start
```

The app will be available at `http://localhost:3000`.

##  Project Structure

```
gemini-resume-matcher/
├── backend/
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   ├── middleware/
│   └── server.js
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   └── App.js
└── README.md
```

##  Future Improvements

- Support for multiple resume formats (PDF, DOCX)
- Resume improvement suggestions alongside gap analysis
- Analytics dashboard tracking preparation progress over time
- Deployment on cloud (AWS/Azure) with CI/CD pipeline

##  Author

**Swastika Kundal**

