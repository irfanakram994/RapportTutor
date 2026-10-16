
# 🎓 RapportTutor

### An Interactive AI Programming Tutor for Python, Java, and C++

RapportTutor is an AI-powered programming tutor designed to make learning programming more interactive, personalized, and engaging. It helps learners understand programming concepts through conversational explanations, interactive quizzes, hints, and feedback adapted to different tutoring styles.

Built with Python, Streamlit, and Groq's LLM API, RapportTutor explores how different AI tutor communication styles may influence learners' perceived rapport, trust, engagement, and comfort when asking for help.

## ✨ Key Features

### 💬 Interactive AI Programming Tutor
- Learn Python, Java, and C++ through conversational interactions.
- Ask questions about programming concepts and code.
- Receive beginner-friendly explanations and examples.
- Get hints and step-by-step guidance.
- Continue learning through follow-up questions rather than long, one-time explanations.

### 🎭 Multiple Tutoring Styles

RapportTutor supports three tutoring styles:

- **Supportive:** Encouraging, patient, and constructive feedback.
- **Neutral:** Clear, direct, and objective explanations.
- **Collaborative:** Interactive problem-solving that encourages learners to reason through problems.

### 🧠 Interactive Programming Quizzes
- Answer programming questions.
- Receive immediate feedback on answers.
- Understand why an answer is correct or incorrect.
- Practise programming fundamentals through short exercises.

### 📋 Learner Experience Survey
Learners can rate their experience across four dimensions:

- Perceived rapport with the tutor
- Trust in the tutor's explanations
- Engagement during learning
- Comfort asking the tutor for help

Optional feedback can help identify opportunities to improve the learning experience.

### 📊 Research Dashboard
- View recorded session events.
- Review quiz attempts and accuracy.
- View available learner survey ratings.
- Explore basic session-level engagement information.

The dashboard is intended for preliminary prototype evaluation, not as a validated measure of learning outcomes.

## 🛠️ Technology Stack

- **Python** — Application logic and AI integration
- **Streamlit** — Interactive web interface
- **Groq API** — AI-powered conversational tutoring
- **OpenAI Python SDK** — API client configured for Groq's compatible endpoint
- **Pandas** — Available for data processing and analysis
- **Google Colab** — Development and execution environment

## 🏗️ How It Works

1. The learner selects a programming language, topic, experience level, and tutoring style.
2. RapportTutor provides a short explanation or responds to a programming question.
3. The learner answers questions, requests hints, or asks follow-up questions.
4. The AI tutor provides feedback according to the selected tutoring style.
5. The learner can complete a survey about their tutoring experience.
6. The research dashboard summarizes information available from the current session.

## 🚀 Getting Started

RapportTutor is designed to run in **Google Colab**.

### Step 1: Open Google Colab

Create a new notebook at:

https://colab.research.google.com/

### Step 2: Install the dependencies

Run the following cell:

```python
!pip -q install streamlit openai pandas
```

### Step 3: Configure your Groq API key

1. Obtain an API key through the Groq developer platform:
   https://console.groq.com/
2. In Google Colab, open **Secrets** in the left sidebar.
3. Add a secret named `GROQ_API_KEY`.
4. Enable notebook access for that secret.

Load the key into the environment:

```python
import os
from google.colab import userdata

os.environ["GROQ_API_KEY"] = userdata.get("GROQ_API_KEY")
```

Do not paste your API key into the notebook source or commit it to GitHub.

### Step 4: Add the application code

Place the RapportTutor Streamlit application code in a Colab cell. Use `%%writefile` to create the application at `/content/app.py`.

For example:

```python
%%writefile /content/app.py

# Place the complete RapportTutor application code here.
```

Replace the placeholder with your actual application code.

### Step 5: Launch the application inside Colab

Run this cell:

```python
import time
from google.colab import output

!pkill -f streamlit

!streamlit run /content/app.py \
    --server.port 8501 \
    --server.enableCORS false \
    --server.enableXsrfProtection false \
    &> /content/streamlit.log &

time.sleep(5)

output.serve_kernel_port_as_iframe(8501, height=1000)
```

The application should appear inside the Colab output area.

If the app does not start, inspect its logs:

```python
!tail -n 80 /content/streamlit.log
```

**Note:** These commands are intended for a trusted, personal Colab environment. Disabling CORS and XSRF protection reduces security protections; do not expose this configuration as a public production deployment.

## 🔐 Privacy and Data Handling

RapportTutor is designed as a research prototype.

- Session events and survey responses are kept in application session memory.
- The application does not intentionally write these research responses to a persistent database or export them to files.
- Session data may disappear when the app session or Colab runtime resets.
- API requests are sent to Groq to generate tutor responses.
- This application's in-memory design does not guarantee that external service providers retain no operational logs.

Do not enter passwords, private identifiers, confidential code, or other sensitive information.

## 🔬 Research Motivation

RapportTutor provides a prototype environment for exploring the relationship between AI tutor communication styles and learners' reported experiences.

Potential research questions include:

- Do learners report different levels of rapport across tutoring styles?
- How does feedback style relate to learners' trust in explanations?
- Do learners feel more comfortable requesting help from some tutor styles?
- How do learners describe their engagement during interactive programming practice?

The current survey is exploratory and should not be treated as a validated psychological instrument. The dashboard provides descriptive session information, not proof of causation.

For a controlled experiment, participants should be assigned to tutoring conditions using an appropriate study design, with consistent learning tasks and clearly documented procedures.

## ⚠️ Limitations

- AI-generated explanations and code may occasionally be incorrect.
- Tutoring quality depends on the selected language model and its availability.
- Session-only data is not a substitute for a research data-management system.
- Survey responses are self-reported and may be influenced by individual preferences.
- Differences observed in a prototype do not establish that one tutoring style is universally better than another.

## 🗺️ Future Improvements

Possible future enhancements include:

- More programming exercises for Python, Java, and C++.
- Adaptive difficulty based on learner performance.
- Code tracing and debugging exercises.
- Structured lesson progression and knowledge checks.
- Better evaluation of tutoring styles through controlled experiments.
- Accessibility and usability improvements.

## 🤝 Contributing

Contributions, bug reports, and suggestions are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Make and test your changes.
4. Submit a pull request describing the improvement.

Please never include API keys or sensitive participant data in contributions.
## Output Preview
<img width="1918" height="1064" alt="image" src="https://github.com/user-attachments/assets/9a91c1bd-bfa6-4f12-88cd-bcb158f936c1" />

<img width="1918" height="1064" alt="image" src="https://github.com/user-attachments/assets/0b83b71d-75d5-43c5-b965-1e57c9b2c897" />
<img width="1915" height="1073" alt="image" src="https://github.com/user-attachments/assets/2ab13785-58ea-4cbe-9f17-75c4f4fd471b" />
<img width="1915" height="1073" alt="image" src="https://github.com/user-attachments/assets/631c6a97-2d34-46c6-be05-dab843192b6a" />
<img width="1918" height="1072" alt="image" src="https://github.com/user-attachments/assets/8146a7a6-434a-4e34-a6b5-12d579ae1e48" />
<img width="1918" height="1072" alt="image" src="https://github.com/user-attachments/assets/a592a7e2-ec21-49f2-a60e-0928517f757f" />
<img width="1919" height="1075" alt="image" src="https://github.com/user-attachments/assets/5f465411-8bed-419f-90be-8f553ad9ca65" />
<img width="1919" height="1075" alt="image" src="https://github.com/user-attachments/assets/839ca462-2a5a-4d00-89a2-70f17ad1c717" />

## 👨‍💻 Author

**Irfan Ali**

RapportTutor — Exploring interactive and personalized AI-assisted programming education.
