# 🚀 MemorAI

**Your AI-Powered Learning Companion**

MemorAI is a full-stack Progressive Web App (PWA) designed to supercharge your learning with scientifically-backed algorithms and AI-driven content generation. Whether you're a student, teacher, or lifelong learner, MemorAI offers personalized spaced repetition, mastery tracking, and engaging visuals to help you remember more, faster! 🎓✨

---

## 📚 Features

- **AI-Generated Flashcards** 🤖🃏: Paste any STEM notes and instantly generate question-answer pairs via a T5-based QG pipeline.
- **Advanced Scheduling** 📈⏳: Combines the SuperMemo-2 (SM-2) algorithm with a Deep Reinforcement Learning (DRL) scheduler for optimal review intervals.
- **Mastery Tracking** 🎯: Bayesian Knowledge Tracing (BKT) models estimate your skill mastery in real time.
- **Offline-First PWA** 💾🌐: Service worker & IndexedDB ensure seamless offline usage and local caching.
- **Concept Graph** 🔗📊: Visualize relationships between concepts with an interactive D3.js force-directed graph.
- **Gamification & Analytics** 🏆📊: Earn badges, track your progress on dashboards powered by Chart.js, and stay motivated!
- **Automatic Image Generation** 🎨🖼️: Generate illustrative images for your flashcards using Stable Diffusion.

---

## 🛠️ Table of Contents

1. [Prerequisites](#-prerequisites)
2. [Installation](#-installation)
   - [Backend](#backend)
   - [Frontend](#frontend)
3. [Running the App](#-running-the-app)
4. [Project Structure](#-project-structure)
5. [Configuration & Tips](#-configuration--tips)
6. [Roadmap & Next Steps](#-roadmap--next-steps)
7. [Contributing](#-contributing)
8. [License](#-license)
9. [Contact](#-contact)

---

## 🔍 Prerequisites

- **Python 3.8+**
- **Node.js & npm (v16+)**
- **Git** (optional, for cloning)

  ## ⚙️ Installation

### Backend

1. Clone the repo and navigate to `backend/`:
   ```cmd
   git clone https://github.com/your-org/memorai.git
   cd memorai/backend
   python3 -m venv venv
   source venv/bin/activate   # Linux/macOS
   venv\\Scripts\\activate    # Windows

   pip install -r requirements.txt


### Frontend

1. navigate to `frontend/`:
   ```cmd
   npm install
   npm start
