# Exam Evaluation System using OCR (Tamil & English)

A simple full-stack project that evaluates **single-page and multi-page handwritten exam answers** using OCR and AI.  
The system extracts answers from images/PDFs and compares them with a **provided answer key + rubrics** to generate an evaluation score.

---

## Features

-  Supports **single and multi-page** exam answer evaluation  
-  **Tamil OCR** using **EasyOCR**  
- 🇬🇧 **English OCR** using **Puter OCR API**  
-  Uses **GPT-5 Nano** (via Puter AI) for automatic evaluation  
-  Evaluates based on **answer key + rubrics**  
-  React frontend + Python backend  
-  Real-time OCR extraction & AI-based scoring  

---

##  How Evaluation Works

1. **Image/PDF is uploaded**
2. Tamil text → extracted using **EasyOCR**  
   English text → extracted using **Puter OCR**  
3. Extracted text is passed into a small **GPT-5 Nano** model:
   ```html
   <script src="https://js.puter.com/v2/"></script>
   <script>
       // Loading ...
       puter.print(`Loading...`);

       // Chat with GPT-5 nano
       puter.ai.chat(`Evaluate this answer`, {
           model: 'gpt-5-nano',
       }).then(puter.print);
   </script>

4. **The model compares :**
- Student answer
- Provided answer key
-  Defined rubrics (accuracy, keywords, completeness, clarity)

A structured score + feedback is returned
Results displayed on React frontend

---

##  Tech Stack

### Frontend
- React (JavaScript)
- Pages for Tamil & English evaluation
- File upload UI + Results display

### Backend
- Python
- EasyOCR for Tamil
- Puter OCR for English
- GPT-5 Nano API for evaluation logic

### AI/OCR

| Task              | Technology        |
|-------------------|-------------------|
| Tamil OCR         | EasyOCR           |
| English OCR       | Puter OCR         |
| Answer Evaluation | GPT-5 Nano (Puter.ai) |



### Project Structure

```
Exam-evaluation-system-using-OCR/
│
├── backend/
│ ├── ocr_service.py # Tamil OCR, English OCR, evaluation logic
│ ├── requirements.txt
│ └── .gitignore
│
├── frontend/
│ ├── src/
│ │ ├── App.js
│ │ ├── Home.js
│ │ ├── EnglishPage.js
│ │ ├── TamilPage.js
│ │ └── index.js
│ ├── package.json
│ └── .gitignore
│
└── README.md
```


##  Setup Instructions

### 1️ Clone the Repository
```git clone https://github.com/aadhisesha/Exam-evaluation-system-using-OCR.git```

```cd Exam-evaluation-system-using-OCR```

###  Backend Setup (Python)
`cd backend`

`pip install -r requirements.txt`

`python ocr_service.py`


### Backend default URL:

http://localhost:5000

###  Frontend Setup (React)
`cd ../frontend`

`npm install`

`npm start`


### Frontend URL:

http://localhost:3000


###  Example Use Case

Upload an answer sheet (single or multi-page)

OCR extracts Tamil/English answers

GPT-5 Nano evaluates using:

Answer key

Rubrics (correctness, completeness, clarity, keywords)

System returns:

Final score

Justification for the marks provided

###  Future Improvements

- Add login system for teachers/students

- Add MCQ + other question types

- PDF report generation

- Store results in a database

- Improve rubric-based scoring accuracy
