
# 📄 Inspecting Rich Documents with Gemini: Multimodality + RAG  
**Course 4 – GenAI Exchange: Google Cloud Challenge Lab**  
*#GenAIExchange*

---

## 🎯 Overview

This challenge lab tested my ability to use **Google's Gemini models** for **multimodal reasoning** and **retrieval-augmented generation (RAG)**. The tasks combined text, image, and video processing with embedding-based retrieval to simulate real-world AI use cases.

🧪 My role: *Marketing Campaign Coordinator* for a media company working with Google  
🧠 My goal: Extract insights from Google brand documents, ads, videos, testimonials, and financials using **Gemini’s multimodal capabilities**.

---

## 🧪 Task 1: Generate Multimodal Insights with Gemini

Gemini is a **multimodal model**, meaning it can understand and respond to a combination of **text, images, and video** in a single prompt.

### ✅ Steps Completed:

1. **Opened Notebook via Vertex AI Workbench**
   - Initialized GenAI SDK for Python using `PROJECT_ID` and `REGION`
   - Ran setup cells and connected kernel: Python 3

2. **Image Understanding Across Multiple Images**
   - Compared images using Gemini to extract visual similarities/differences

3. **Compare Image Content**
   - Described elements and common traits across multiple media brand assets

4. **Generate Video Description**  
   Used the video URL below as input to Gemini:
```

[https://storage.googleapis.com/spls/gsp520/google-pixel-8-pro.mp4](https://storage.googleapis.com/spls/gsp520/google-pixel-8-pro.mp4)

```
- Gemini generated a description of the scene, product highlights, and message intent

5. **Extract Object Tags Throughout the Video**
- Extracted visual objects that persist throughout the video (e.g., device, hands, motion, environment)

6. **Ask Questions About the Video**
- Asked follow-up questions such as:
  - "What’s the main product shown?"
  - "What emotion is being portrayed?"
  - "How would you caption this?"

7. **Retrieve Extra Information Beyond the Video**
- Added supplementary image and text data for deeper analysis
- Gemini was able to reference both visual and text-based content

---

## 🔍 Task 2: Retrieval and Knowledge Integration with Multimodal RAG

In this task, I implemented **Multimodal RAG** — combining Gemini’s language abilities with **retrieved document snippets** and **image metadata** to answer grounded queries.

### 🧾 Documents Used:

1. **Google Terms of Service (Text)**
- Legal structure of user-Google relationship

2. **Modified Google 10-K (Text + Visual)**
- Contained 14 pages split into two parts
- Included graphs, tables, and key metrics

---

## ⚙️ Tools and Helper Functions Used

To simulate RAG, the lab provided helper functions that worked on pre-processed document metadata:

### 🧠 Text Metadata Functions:
- `text`, `chunk_text`: Original full text and chunked segments
- `text_embedding_chunk`: Embedding for each chunk
- `get_similar_text_from_query(query)`: Returns top-matching text chunks
- `print_text_to_text_citation()`: Shows source & citation for retrieved texts

### 🖼️ Image Metadata Functions:
- `img_desc`: Gemini-generated description of image
- `mm_embedding_from_text_desc_and_img`: Joint embedding of image + text
- `get_similar_image_from_query(img)`: Finds matching images
- `print_text_to_image_citation()`: Shows source image citation

---

## 💡 Final Multimodal RAG Flow

1. **Build Document Metadata**  
→ Parsed text and images, generated embeddings

2. **Create a User Query**
→ Example: "What are the risks discussed in the 10-K?"

3. **Retrieve Relevant Chunks**
→ Used `get_similar_text_from_query()` to fetch relevant content

4. **Organize Chunks as Context**
→ Formatted the response-ready context block

5. **Pass Context to Gemini**
→ Called `get_gemini_response()` with context + original question

6. **Display Citations**
→ Verified sources of retrieved data using helper citation functions

---

## 🧠 What I Learned

- Gemini can **seamlessly switch modalities** in a single interaction
- **Embedding-based retrieval** is powerful for grounding LLM responses
- RAG is a **production-ready design pattern** for GenAI apps needing source-backed answers
- Gemini can parse **videos, text, images**, and fuse them for rich QA

---

## 👨‍💻 Author

Created as part of the **Google #GenAIExchange**  By https://github.com/ayushiroully

