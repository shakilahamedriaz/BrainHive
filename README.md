# 🧠 BrainHive: An AI-Powered Knowledge Sharing Platform



<p align="center">
A sophisticated, full-stack knowledge sharing platform built with Django and Python. BrainHive is designed for creating and sharing content, supercharged with modern AI features including an automatic post summarizer and a knowledgeable RAG-based chatbot to create an intelligent user experience.
</p>

---

## ✨ Core Features & Technical Highlights

This project demonstrates a comprehensive understanding of full-stack web development and the practical application of modern AI technologies.

---

### 🔧 Core Application (Backend & Frontend)

- **Secure User Authentication**  
  Full user lifecycle management including registration, login/logout, and profile management using Django's built-in auth system.

- **Full CRUD Functionality**  
  Robust implementation of Create, Read, Update, and Delete operations for blog posts, ensuring users have complete control over their content.

- **Rich Text Editing**  
  Integrated `django-ckeditor` to provide a powerful WYSIWYG editor for an enhanced writing experience.

- **Advanced Search & Filtering**  
  Dynamic server-side search functionality combined with filtering by categories and tags for efficient content discovery.

- **Interactive UI**  
  A clean, professional, and fully responsive user interface built from scratch with Tailwind CSS and made interactive with Alpine.js.

- **Database & ORM Mastery**  
  Efficient data modeling and querying using the Django ORM with a relational SQLite database.

---

## 🤖 Artificial Intelligence Integration

- **AI-Powered Summarization**  
  Leverages the **Groq API** (with LLaMA 3) to automatically generate and save concise summaries for every blog post, triggered on the model's save method. This demonstrates knowledge of API integration within the Django model lifecycle.

- **Retrieval-Augmented Generation (RAG) Chatbot**  
  A custom-built AI chatbot that answers user questions based only on the knowledge within the platform's articles. This is a key feature demonstrating advanced AI implementation skills.

---

### 💡 AI System Design: The RAG Chatbot

The chatbot is not a simple API call; it's a complete RAG pipeline that ensures answers are accurate and grounded in the provided content.

- **Indexing (`index_posts.py`)**  
  A custom Django management command processes all posts. It uses the `sentence-transformers` library to convert the text into numerical vector embeddings. These embeddings are stored in a highly efficient FAISS vector index.

- **Retrieval**  
  When a user asks a question, their query is also converted into an embedding. The FAISS index is then searched to find the most semantically similar post chunks (the "context").

- **Augmentation & Generation**  
  This retrieved context is then injected into a carefully crafted prompt that is sent to the Groq API's LLaMA 3 model. The model is instructed to formulate an answer strictly based on this context, preventing AI hallucinations and creating a truly knowledgeable assistant.

---

## 🛠️ Tech Stack

| Category       | Technology                                       |
|----------------|--------------------------------------------------|
| **Backend**    | Python, Django                                   |
| **Frontend**   | Tailwind CSS, Alpine.js                          |
| **Database**   | SQLite 3                                         |
| **AI API**     | Groq (LLaMA 3 Model)                             |
| **AI/ML Libs** | sentence-transformers, faiss-cpu, beautifulsoup4 |
| **Tooling**    | django-ckeditor, django-widget-tweaks, python-dotenv |

---

