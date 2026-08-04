Study Success Week: From AI Concepts to Deployable Applications

«Revision week theme: We will revise core computing concepts and explore how artificial intelligence can be turned into practical software that runs on a personal computer.»

What Are We Learning Today?

This session presents artificial intelligence from a developer’s perspective.

Instead of concentrating only on mathematical theory or research papers, we will examine how developers:

1. Set up a development environment.
2. use AI and machine-learning models.
3. connect models to files, APIs and software tools.
4. build local AI agents.
5. process documents such as résumés and PDFs.
6. create user interfaces.
7. package Python applications.
8. install applications directly from GitHub.
9. evaluate whether an AI system is useful, safe and reliable.

---

Learning Outcomes

By the end of this session, students should be able to:

- distinguish between AI, machine learning, deep learning, LLMs and AI agents;
- explain how an AI model becomes part of a complete software application;
- describe how text embeddings and similarity scores can rank documents;
- understand how an AI agent uses models, memory and tools;
- create and activate a Python environment;
- install Python dependencies using "pip" or Conda;
- install a Python package directly from GitHub;
- write a structured prompt;
- identify privacy, security and reliability risks in AI applications;
- plan a small AI-powered software project.

---

1. The AI Landscape

Artificial intelligence is the broad field of building computer systems that perform tasks that normally require human intelligence.

Machine learning, deep learning and large language models are all parts of this wider field.

flowchart LR
    A[Artificial Intelligence] --> B[Machine Learning]
    B --> C[Deep Learning]
    C --> D[Foundation Models]
    D --> E[Large Language Models]
    E --> F[AI Agents]
    F --> G[Deployed AI Applications]

Important Definitions

Concept| Simple explanation| Example
Artificial intelligence| The broad goal of making computers perform intelligent tasks| A planning or recommendation system
Machine learning| Algorithms learn patterns from data| Predicting house prices
Deep learning| Machine learning using multi-layer neural networks| Image recognition
Foundation model| A large model trained on broad data and adaptable to many tasks| A general language or vision model
Large language model| A foundation model designed to process and generate language| A coding or question-answering assistant
AI agent| A system that combines a model with instructions, memory and tools| An assistant that searches files and performs tasks
Deployment| Making a model or application available to users| Local app, website, API or mobile application

---

2. How a Large Language Model Works

A large language model processes text as smaller units called tokens.

During training, the model learns statistical relationships between tokens. During use, it predicts an appropriate continuation based on:

- the user’s request;
- system instructions;
- previous conversation;
- supplied documents;
- retrieved information;
- available tools;
- the model’s learned parameters.

flowchart LR
    A[User text] --> B[Tokenisation]
    B --> C[Model processing]
    C --> D[Token probabilities]
    D --> E[Generated response]

An LLM does not reason or understand the world exactly as a human does. It models language patterns extremely effectively and can perform tasks that appear to require understanding.

This capability allows developers to use language as an interface for software.

Instead of manually clicking through many menus, a user might write:

«Find the jobs most relevant to my résumé, rank them and explain why each job matches my experience.»

The model can interpret the request, but other software components must retrieve the jobs, read the résumé, calculate scores and display the results.

---

3. From an LLM to an AI Agent

A chatbot mainly generates responses.

An agent goes further by using tools and taking controlled actions.

A typical agent contains:

- an LLM;
- system instructions;
- tools;
- short-term context;
- optional long-term memory;
- files or databases;
- permissions;
- validation and safety rules.

flowchart TD
    U[User] --> I[Chat or application interface]
    I --> A[AI agent]

    A --> L[Language model]
    A --> M[Memory]
    A --> T[Tool selection]

    T --> F[Local files]
    T --> W[Web or APIs]
    T --> D[Database]
    T --> C[Code execution]
    T --> E[Email, calendar or other services]

    F --> V[Validation]
    W --> V
    D --> V
    C --> V
    E --> V

    V --> A
    A --> R[Response or approved action]

The Agent Loop

A simplified agent loop is:

1. Receive a goal.
2. understand the request.
3. decide whether a tool is needed.
4. select a tool.
5. provide the tool with arguments.
6. inspect the result.
7. check whether the goal has been completed.
8. respond or continue with another step.

Goal
  ↓
Plan
  ↓
Choose tool
  ↓
Run tool
  ↓
Observe result
  ↓
Validate result
  ↓
Respond or continue

Important Human Responsibility

AI agents should not replace human responsibility or judgement.

They are most useful for:

- repetitive tasks;
- information retrieval;
- document processing;
- drafting;
- classification;
- ranking;
- workflow automation;
- controlled tool use.

People should remain responsible for:

- defining the goal;
- reviewing important outputs;
- approving destructive actions;
- checking factual claims;
- protecting private information;
- deciding whether the result is appropriate.

---

4. Demonstration One: A Personal Local AI Agent

Example: OpenClaw Personal AI Assistant

Repository:

"https://github.com/MuhammadMuneeb007/openclaw" (https://github.com/MuhammadMuneeb007/openclaw)

A personal AI agent can run on a user-controlled computer and connect to authorised tools and communication channels.

The demonstration can be used to explain:

- the difference between a model and an agent;
- local-first versus cloud-based applications;
- model configuration;
- tool permissions;
- agent memory;
- communication channels;
- automation;
- privacy;
- prompt-injection risks;
- human approval.

Questions to Consider During the Demonstration

- Where is the agent running?
- Which model is being used?
- Which information can the agent access?
- Which tools can it call?
- Is the information stored locally?
- Can the user inspect the agent’s actions?
- What happens when a tool fails?
- Can the agent perform a destructive action?
- Does the action require confirmation?
- How could an attacker manipulate the agent?

Local Agent Architecture

flowchart LR
    U[User] --> UI[Local interface]
    UI --> G[Agent gateway]
    G --> L[LLM]
    G --> S[Skills and tools]
    S --> P[Personal files]
    S --> B[Browser]
    S --> API[External APIs]
    S --> APP[Authorised applications]
    G --> LOG[Logs and history]
    G --> UI

Safety Principle

Give an agent the minimum level of access required for the task.

For example, an agent that summarises documents should not automatically receive permission to:

- delete files;
- uninstall applications;
- send emails;
- publish content;
- access unrelated folders.

---

5. Demonstration Two: AI-Powered Job Ranking

Project

JobsDownloaderAndRanker

"https://github.com/MuhammadMuneeb007/JobsDownloaderAndRanker" (https://github.com/MuhammadMuneeb007/JobsDownloaderAndRanker)

This project demonstrates an end-to-end applied AI pipeline.

It retrieves jobs, processes their descriptions, reads a résumé and ranks the jobs according to their relevance to the candidate.

System Pipeline

flowchart LR
    A[SEEK, Indeed and LinkedIn] --> B[Download job listings]
    B --> C[Clean HTML and normalise text]
    C --> D[Remove duplicate jobs]

    E[Résumé PDF] --> F[Extract text]
    F --> G{Text available?}
    G -->|Yes| H[Use extracted text]
    G -->|No| I[Run OCR]
    I --> H

    D --> J[Job text representations]
    H --> K[Résumé representation]

    J --> L[Semantic similarity]
    K --> L

    J --> M[Keyword and TF-IDF similarity]
    K --> M

    J --> N[Skill overlap]
    K --> N

    J --> O[Title and domain matching]
    K --> O

    L --> P[Combined ranking score]
    M --> P
    N --> P
    O --> P

    P --> Q[Ranked CSV]
    Q --> R[Local Dash application]

AI Concepts Demonstrated

Data collection

The system collects information from multiple sources.

This introduces:

- web requests;
- APIs;
- wrappers;
- HTML parsing;
- browser automation;
- rate limits;
- terms of service;
- error handling.

Data cleaning

Job descriptions may contain:

- HTML tags;
- repeated records;
- inconsistent spacing;
- missing values;
- different column names;
- incomplete descriptions.

A model will not automatically correct every data-quality problem. Developers must build a reliable preprocessing pipeline.

PDF processing

A résumé may be:

- a text-based PDF;
- a scanned PDF;
- an image;
- a document with a complex layout.

The application first attempts normal text extraction and can use OCR when the text cannot be extracted directly.

Embeddings

An embedding converts text into a numerical vector.

Texts with similar meanings should have vectors that are closer together.

Résumé text ──────► embedding vector
Job description ─► embedding vector
                         │
                         ▼
                 similarity score

For example:

Résumé: "Developed deep-learning models using PyTorch"

Job A: "Looking for a machine-learning engineer with PyTorch experience"
Job B: "Looking for a retail store assistant"

The embedding for the résumé should be closer to Job A than Job B.

Multiple ranking signals

A robust ranking system should not rely on only one score.

The JobRanker combines signals such as:

- semantic similarity;
- TF-IDF similarity;
- job-title similarity;
- technical-skill overlap;
- domain relevance;
- location preferences;
- mismatch penalties.

This is an example of a hybrid ranking system.

Final score =
    semantic similarity
  + keyword similarity
  + skill overlap
  + title relevance
  + domain relevance
  - mismatch penalties

Explainability

A ranking is more useful when the user can see:

- matched skills;
- missing skills;
- semantic score;
- keyword score;
- final score;
- explanation for the ranking.

This allows the user to evaluate the recommendation rather than blindly trusting it.

---

Running the JobRanker

git clone https://github.com/MuhammadMuneeb007/JobsDownloaderAndRanker.git
cd JobsDownloaderAndRanker

Create the environment:

conda env create -f environment.yml
conda activate n8n-env

Run the pipeline:

python Step1-DownloadJobsFromSeek.py
python Step2-CleanFile.py
python Step3-OCR-BERT-Rank.py
python Step3.1-OCR-BERT-Rank-Display.py

Open the local application:

http://127.0.0.1:8050/

Development Discussion

Students should consider:

- What happens when a website changes its HTML?
- How should duplicate jobs be detected?
- Should all ranking features have equal weights?
- How can the ranking be evaluated?
- Can historical user choices improve the ranking?
- Could the system unfairly penalise a candidate?
- What private information is contained in a résumé?
- Should a résumé be uploaded to an external service?
- How should credentials and API keys be stored?

---

6. Demonstration Three: Installing a Python Application from GitHub

Project

SystemSieve

"https://github.com/MuhammadMuneeb007/SystemSieve" (https://github.com/MuhammadMuneeb007/SystemSieve)

SystemSieve is a Windows utility for reviewing installed software, checking updates and examining storage usage.

This is primarily a software-engineering and deployment demonstration rather than an AI model demonstration.

It shows how a Python project can become an installable application.

Install Directly from GitHub

py -m pip install "git+https://github.com/MuhammadMuneeb007/SystemSieve.git@main"

After installation:

systemsieve doctor
systemsieve gui

What Does This Command Mean?

py
└── Run the Python launcher

-m pip
└── Run pip using this Python installation

install
└── Install a package

git+https://...
└── Obtain the package source from a Git repository

@main
└── Install from the main branch

Developer Lessons from SystemSieve

The project can introduce:

- Python package structure;
- "pyproject.toml";
- dependencies;
- package metadata;
- command-line entry points;
- graphical interfaces;
- local SQLite databases;
- background workers;
- logging;
- tests;
- linting;
- release builds;
- GitHub Actions;
- safety controls.

Dry Run and Destructive Operations

Applications that delete files or uninstall software should not perform destructive actions without confirmation.

A safer design is:

flowchart LR
    A[User selects operation] --> B[Generate plan]
    B --> C[Preview only]
    C --> D[User reviews command]
    D --> E{Approve execution?}
    E -->|No| F[Cancel]
    E -->|Yes| G[Run validated operation]
    G --> H[Record result]

Important safety mechanisms include:

- preview mode;
- protected paths;
- validated commands;
- confirmation screens;
- logs;
- clear error reporting;
- restore or recovery options;
- least-privilege execution.

---

7. AI-Powered Programming Assistants

Example Project

AI-Powered Python Learning Assistant

"https://github.com/MuhammadMuneeb007/AI-Powered-Python-Learning-Assistant" (https://github.com/MuhammadMuneeb007/AI-Powered-Python-Learning-Assistant)

This project combines:

- an AI chat interface;
- code generation;
- a Python editor;
- file uploads;
- code execution;
- result display;
- downloadable outputs;
- a Streamlit web interface.

Application Architecture

flowchart LR
    A[Student question] --> B[LLM]
    B --> C[Generated explanation]
    B --> D[Generated Python code]
    D --> E[Code editor]
    E --> F[Execution environment]
    F --> G[Output or error]
    G --> H[Student reviews result]

Critical Security Lesson

Generated code must not automatically be trusted.

Running model-generated code can expose a system to:

- file deletion;
- credential theft;
- malicious network requests;
- infinite loops;
- excessive memory usage;
- unwanted package installation;
- access to private files.

Production systems should execute untrusted code inside a restricted sandbox or container.

---

8. Domain-Specific LLMs

Example Project

BioStarsGPT

"https://github.com/MuhammadMuneeb007/BioStarsGPT" (https://github.com/MuhammadMuneeb007/BioStarsGPT)

A general LLM knows broad language patterns, but it may not be sufficiently accurate in a specialised field.

A domain-specific system may use:

- specialised datasets;
- prompt engineering;
- retrieval-augmented generation;
- supervised fine-tuning;
- human evaluation;
- automatic evaluation;
- citation checking.

Simplified Domain-Model Pipeline

flowchart LR
    A[Domain sources] --> B[Collect data]
    B --> C[Clean and filter]
    C --> D[Convert to structured examples]
    D --> E[Train and validation split]
    E --> F[Fine-tune or retrieve]
    F --> G[Evaluate]
    G --> H[Deploy]
    H --> I[Monitor and improve]

Important Dataset Questions

Before training or fine-tuning, developers should ask:

- Who created the data?
- Can the data legally be reused?
- Does it contain personal information?
- Are the answers accurate?
- Is the dataset representative?
- Are there duplicated examples?
- Is the test set separated from the training set?
- How will hallucinations be detected?
- Should the model provide citations?

---

9. Prompt Engineering

Prompt engineering means designing instructions that help a model produce a useful and testable output.

A strong prompt normally contains:

1. role;
2. goal;
3. context;
4. input;
5. constraints;
6. output format;
7. examples;
8. verification instructions.

Prompt Template

Role:
You are a...

Goal:
Your task is to...

Context:
The user is working with...

Input:
The following information is available...

Constraints:
- Do not...
- Only use...
- Keep the answer...
- Ask for confirmation before...

Output format:
Return the result as...

Quality checks:
Before answering, verify that...

Weak Prompt

Rank these jobs.

Improved Prompt

You are a job-matching assistant.

Compare the supplied résumé with each job description.

For every job:

1. calculate a match score from 0 to 100;
2. identify matching technical skills;
3. identify important missing skills;
4. explain the score in no more than three sentences;
5. do not infer experience that is not present in the résumé.

Return a table with these columns:

Rank | Job title | Match score | Matching skills | Missing skills | Explanation

Prompt Engineering Is Not Enough

A good prompt cannot solve every problem.

Reliable AI applications also need:

- good input data;
- appropriate tools;
- deterministic code;
- validation;
- structured outputs;
- tests;
- monitoring;
- human review.

---

10. Working with PDFs and Documents

Many practical AI applications process documents.

A typical document-question-answering pipeline is:

flowchart LR
    A[PDF or document] --> B{Contains selectable text?}
    B -->|Yes| C[Extract text]
    B -->|No| D[OCR]
    D --> C
    C --> E[Clean text]
    E --> F[Split into chunks]
    F --> G[Create embeddings]
    G --> H[Store vectors]
    I[User question] --> J[Retrieve relevant chunks]
    H --> J
    J --> K[LLM]
    K --> L[Answer with sources]

Document AI Concepts

Text extraction

Used for digitally generated PDFs.

Optical character recognition

Used when a PDF contains scanned pages or images.

Chunking

Large documents are separated into smaller sections.

Embeddings

Each section is transformed into a numerical representation.

Retrieval

The system selects the sections most relevant to the user’s question.

Generation

The LLM creates an answer using the retrieved sections.

Citation

The system should identify which document sections support the answer.

---

11. Setting Up a Python Development Environment

A development environment keeps project dependencies organised and reduces conflicts between projects.

First Check Your Installation

Open Command Prompt, PowerShell, Anaconda Prompt or Miniforge Prompt.

python --version
py --version
where python
git --version
conda --version

---

Option A: Conda Environment

Create an environment:

conda create -n applied-ai python=3.11 -y

Activate it:

conda activate applied-ai

Install packages:

python -m pip install pandas scikit-learn sentence-transformers streamlit

View environments:

conda info --envs

View installed packages:

conda list

Export the environment:

conda env export > environment.yml

Recreate an environment from a file:

conda env create -f environment.yml

Deactivate:

conda deactivate

---

Option B: Standard Python Virtual Environment

Create a virtual environment:

py -m venv .venv

Activate it in Command Prompt:

.venv\Scripts\activate

Activate it in PowerShell:

.venv\Scripts\Activate.ps1

Upgrade "pip":

python -m pip install --upgrade pip

Install dependencies:

python -m pip install -r requirements.txt

Save installed packages:

python -m pip freeze > requirements.txt

Deactivate:

deactivate

---

12. Essential Command-Line Commands

Navigation

dir
cd folder-name
cd ..
cd \
mkdir new-folder
rmdir folder-name
cls

Working with Files

type filename.txt
copy source.txt destination.txt
move file.txt folder
del filename.txt

Python

python --version
python script.py
python -m pip --version
python -m pip list
python -m pip install package-name
python -m pip uninstall package-name

Git

git clone REPOSITORY_URL
git status
git add .
git commit -m "Describe the change"
git pull
git push

Useful Diagnostics

where python
where pip
where git
where conda
python -c "import sys; print(sys.executable)"
python -m pip check

Using "python -m pip" is preferable to typing only "pip" because it makes the Python installation being used more explicit.

---

13. How an AI Application Is Deployed

A model alone is not a complete product.

The complete system may include:

flowchart TD
    A[User interface] --> B[Application backend]
    B --> C[Model or model API]
    B --> D[Database]
    B --> E[Files or object storage]
    B --> F[External APIs]
    B --> G[Authentication]
    B --> H[Logging and monitoring]

Common Deployment Levels

Level| Example| Suitable for
Python script| "python app.py"| Experiments and automation
Notebook| Jupyter Notebook| Exploration and teaching
Local GUI| Desktop Python application| Personal tools
Local web application| Streamlit or Dash| Demonstrations and internal tools
API| FastAPI or Flask| Connecting AI to other software
Container| Docker| Reproducible deployment
Cloud application| Vercel, Azure, AWS or Google Cloud| Public or organisational access
Mobile or edge application| On-device model| Offline and privacy-sensitive use

Typical Development Progression

Idea
  ↓
Small Python script
  ↓
Test with sample data
  ↓
Create reusable functions
  ↓
Add a command-line interface
  ↓
Add a graphical or web interface
  ↓
Package the project
  ↓
Add tests
  ↓
Create a release
  ↓
Deploy and monitor

---

14. Developer Checklist for an AI Project

Problem

- What problem are we solving?
- Who is the user?
- Does the task actually require AI?
- What would a non-AI solution look like?

Data

- Where does the data come from?
- Is collection permitted?
- Is the data accurate?
- Does it contain private information?
- How will it be cleaned?

Model

- Which model is appropriate?
- Can it run locally?
- How much memory does it require?
- Is an external API necessary?
- What is the cost?

Application

- How will the user provide input?
- How will the output be displayed?
- Which tools can the system access?
- What happens when a dependency fails?

Evaluation

- What does a good answer look like?
- Which metrics will be used?
- Will humans review the output?
- How will hallucinations be detected?
- How will incorrect actions be prevented?

Deployment

- Where will the application run?
- How will dependencies be installed?
- Where will secrets be stored?
- How will the system be updated?
- How will errors be monitored?

---

15. Suggested Classroom Activities

Activity 1: Improve a Prompt

Give students a vague prompt:

Tell me about this job.

Ask them to rewrite it using:

- role;
- goal;
- context;
- constraints;
- output format;
- verification.

---

Activity 2: Design a Ranking Formula

Ask students to assign weights to:

- semantic similarity;
- technical skills;
- job-title similarity;
- location;
- education;
- experience;
- missing essential skills.

Example:

Final score =
    40% semantic similarity
  + 25% skill overlap
  + 15% title similarity
  + 10% domain relevance
  + 10% location preference

Students should explain why they selected their weights.

---

Activity 3: Design an Agent

Choose one task:

- revision assistant;
- university timetable assistant;
- assignment organiser;
- document-search agent;
- personal expense assistant;
- job-search assistant.

Define:

Goal:
Inputs:
Model:
Tools:
Memory:
Output:
Permissions:
Risks:
Human approval:

---

Activity 4: Install a GitHub Package

Students inspect a repository and identify:

- the README;
- licence;
- installation command;
- dependencies;
- source directory;
- tests;
- issues;
- releases;
- security documentation.

They then determine whether they trust the package enough to install it.

«Never install an unfamiliar package without reviewing its repository, source, permissions and reputation.»

---

Activity 5: Explain the JobRanker Pipeline

Students explain each stage:

Download
→ clean
→ extract résumé
→ represent text
→ calculate similarities
→ combine scores
→ rank
→ display

The goal is to distinguish between:

- normal programming;
- data engineering;
- machine learning;
- user-interface development;
- deployment.

---

16. Possible Extension Projects

Students could extend the demonstrations by building:

- a cover-letter generator using ranked job information;
- a résumé skill-gap analyser;
- an assignment-question classifier;
- a local document-question-answering system;
- an AI revision chatbot;
- a course-material search tool;
- an explainable recommendation system;
- a Streamlit interface for an existing Python script;
- a FastAPI endpoint for a trained model;
- a Docker container for a Python application;
- a safe agent that organises files in preview mode.

---

17. Learning Roadmap

A practical learning order is:

flowchart TD
    A[Command line basics] --> B[Python fundamentals]
    B --> C[Git and GitHub]
    C --> D[Data handling with Pandas]
    D --> E[Machine-learning fundamentals]
    E --> F[Neural networks and PyTorch]
    F --> G[NLP and transformers]
    G --> H[Prompt engineering]
    H --> I[Embeddings and retrieval]
    I --> J[LLM applications]
    J --> K[Agents and tool use]
    K --> L[APIs, Docker and deployment]
    L --> M[Evaluation, safety and monitoring]

---

18. Recommended Resources

Python and Development Environments

- Python tutorial:
  "https://docs.python.org/3/tutorial/" (https://docs.python.org/3/tutorial/)

- Installing packages with "pip" and "venv":
  "https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/" (https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/)

- Conda getting-started guide:
  "https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html" (https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html)

- Conda environment management:
  "https://docs.conda.io/projects/conda/en/stable/user-guide/tasks/manage-environments.html" (https://docs.conda.io/projects/conda/en/stable/user-guide/tasks/manage-environments.html)

- Conda documentation in PDF format:
  "https://docs.conda.io/_/downloads/conda/en/latest/pdf/" (https://docs.conda.io/_/downloads/conda/en/latest/pdf/)

Git and GitHub

- GitHub getting started:
  "https://docs.github.com/en/get-started" (https://docs.github.com/en/get-started)

- Git documentation:
  "https://git-scm.com/doc" (https://git-scm.com/doc)

- Pro Git book:
  "https://git-scm.com/book/en/v2" (https://git-scm.com/book/en/v2)

AI and Machine Learning

- Machine Learning roadmap:
  "https://roadmap.sh/machine-learning" (https://roadmap.sh/machine-learning)

- AI Engineer roadmap:
  "https://roadmap.sh/ai-engineer" (https://roadmap.sh/ai-engineer)

- Prompt Engineering roadmap:
  "https://roadmap.sh/prompt-engineering" (https://roadmap.sh/prompt-engineering)

- LLM Engineer roadmap:
  "https://roadmap.sh/r/llm-engineer-ay1q6" (https://roadmap.sh/r/llm-engineer-ay1q6)

- Hugging Face LLM course:
  "https://huggingface.co/learn/llm-course/chapter1/1" (https://huggingface.co/learn/llm-course/chapter1/1)

- PyTorch beginner tutorials:
  "https://pytorch.org/tutorials/beginner/basics/intro.html" (https://pytorch.org/tutorials/beginner/basics/intro.html)

- Scikit-learn tutorials:
  "https://scikit-learn.org/stable/tutorial/index.html" (https://scikit-learn.org/stable/tutorial/index.html)

Application Development and Deployment

- Streamlit documentation:
  "https://docs.streamlit.io/" (https://docs.streamlit.io/)

- Plotly Dash documentation:
  "https://dash.plotly.com/" (https://dash.plotly.com/)

- FastAPI tutorial:
  "https://fastapi.tiangolo.com/tutorial/" (https://fastapi.tiangolo.com/tutorial/)

- Docker getting started:
  "https://docs.docker.com/get-started/" (https://docs.docker.com/get-started/)

- Mermaid diagrams:
  "https://mermaid.js.org/intro/" (https://mermaid.js.org/intro/)

---

19. Key Message

Artificial intelligence is not only a model.

A useful AI product normally combines:

problem definition
+ data
+ model
+ prompts
+ deterministic code
+ tools
+ interface
+ storage
+ security
+ evaluation
+ deployment

The strongest AI developers are not simply people who know how to call an LLM.

They understand how to transform a model into a reliable, explainable, secure and useful software system.

---

Exit Questions

Before leaving, students should be able to answer:

1. What is the difference between machine learning and deep learning?
2. What makes an LLM different from an AI agent?
3. Why do developers use virtual environments?
4. What is a text embedding?
5. How can a résumé and job description be compared?
6. Why should an AI ranking system provide explanations?
7. What happens when we run "pip install" from a GitHub repository?
8. Why should destructive actions use preview mode?
9. What information belongs in a strong prompt?
10. What additional components are required to deploy an AI model?
