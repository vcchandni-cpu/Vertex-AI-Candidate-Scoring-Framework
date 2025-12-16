# 🤖 Vertex AI Candidate Scoring Framework

## 🏆 Project Summary: No-Code GenAI Deployment on Vertex AI

This project showcases the development and deployment of a highly reusable **AI Resume-Job Match Scoring Tool** entirely within the **Google Vertex AI Studio** interface. The solution provides a scalable, enterprise-grade Applicant Tracking System (ATS) function without writing any custom backend code.


### ✨ Key Accomplishments

| Achievement | Technical Skill Demonstrated |
| :--- | :--- |
| **Dynamic, Job-Agnostic Engine** | Designed a base prompt with **variable inputs** (Job Description, Resume) allowing the tool to score candidates for **any new vacancy** instantly. |
| **Reliable Structured Output** | Configured the Gemini model to return a consistent object (score, justification, gaps). |
| **Rigorous Model Tuning** | Used the **Compare function** to finalize optimal parameters (e.g., low **Temperature**, disabled **Grounding**) ensuring the scoring is **deterministic** and unbiased. |
| **Rapid Serverless Deployment** | Utilized the **Vertex AI Studio "Deploy App"** feature for one-click deployment to **Google Cloud Run**, validating a fast time-to-market workflow. |

---

## 💻 Implementation & Architecture

The application's intelligence is rooted in the strategic setup of the Gemini model within the Vertex AI Studio.

### 1. Prompt Engineering & Variable Inputs

The core logic is captured in a **System Message** that instructs the model to act as a strict scorer. The Job Description and Resume content are passed as dynamic variables, making the prompt reusable across different roles.

* **System Message (The Constant):** You are a resume analyzer.
Your primary goal is to help recruiters by accurately and concisely summarizing resume information and highlighting match words.
Focus only on the information provided in the prompt. Do not invent details. 
Maintain a professional and objective tone
use less than 100 words.

* **Prompt Variables (The Dynamics):**
    * `JOB_DESCRIPTION`: Uploaded for each new vacancy.
    * `APPLICANT_RESUME`: Uploaded for the candidate being evaluated.

### 2. Model Tuning for Consistency (The Scorer's Reliability)

To ensure the match score is consistent and reliable, I rigorously adjusted the following parameters in Vertex AI Studio:

| Parameter | Setting Used | Rationale |
| :--- | :--- | :--- |
| **Temperature** | Low (e.g., 0) | Forces the model to select the most probable (deterministic) tokens, eliminating creativity and ensuring consistent scoring logic. |
| **Grounding** | **OFF** | Prevents external web search, forcing the model to score based *only* on the provided Resume and JD content. |
| **Compare Feature** | Used to A/B test parameter sets | Validated which combination of model version and settings yielded the most accurate and stable scoring results. |

### 3. Serverless Deployment Workflow

The final, tuned prompt was deployed using the **"Deploy App"** function, demonstrating a secure and scalable deployment strategy:

## 🖼️ Visual Showcase

*\[**Placeholder for Screenshot A: Vertex AI Studio Prompt Configuration**]*
*Show a screenshot of the prompt window in Vertex AI Studio, highlighting the System Message, the two Variable Input fields, and the model parameters (Temperature, Top-P) in the sidebar.*
![Vertex AI Prompt Configuration](assets/screenshot-A-prompt.png)
---

## 📊 Example Structured Output

The tool consistently generates a structured output.
## 🚀 Live Demonstration (GIF)

Watch the tool generate a score instantly upon entering the data:

![AI Scoring Demo GIF](assets/app-demo.gif)
---
## 🔒 Project Environment Note

This project was developed as part of a Google Certification Lab environment and is not available as a public, live endpoint. The screenshots provided demonstrate the configuration and deployment steps taken within the restricted environment.

---
