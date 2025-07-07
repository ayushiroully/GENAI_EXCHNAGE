## 🚀 Scenario

As a **developer at an AI startup** specializing in **video content analysis**, I was challenged to build three crucial features using **Gemini's APIs**:

- ✍️ Generate polished, contextual **text responses**
- 🧠 Trigger **function calls** using LLM instructions
- 🎬 Perform **video content analysis** using Gemini’s multimodal capabilities

The lab simulated a production-like use case, and I implemented working demos for each using **Vertex AI, Cloud Shell, and Gemini APIs**.

---

## 🧪 Task 1: Generate Text with Gemini Flash API

In this step, I made direct API calls using `curl` from **Cloud Shell** to verify Gemini's text generation behavior.

### ✅ Enabled Required APIs

* Vertex AI API
* IAM and Cloud Resource Manager APIs

### 📡 Sent a Prompt via `curl`

**Prompt**:

> Why is the sky blue?

```bash
curl \
  -X POST \
  -H "Authorization: Bearer $(gcloud auth print-access-token)" \
  -H "Content-Type: application/json" \
  https://${API_ENDPOINT}/v1/projects/${PROJECT_ID}/locations/${LOCATION}/publishers/google/models/${MODEL_ID}:streamGenerateContent \
  -d '{
    "contents": [{
      "role": "user",
      "parts": [{ "text": "Why is the sky blue?" }]
    }]
  }'
```

### 💬 Gemini Output

Gemini returned a detailed scientific explanation involving **Rayleigh scattering** — confirming that text generation works via direct API integration.

---

## 💻 Task 2: Open and Configure Vertex AI Workbench

✅ Ready to run function call and video tasks in an interactive notebook.

---

## 🧠 Task 3: Function Calling with Gemini

### 🔄 Goal:

Simulate a scenario where Gemini receives a user prompt and **calls a weather function** dynamically based on the intent.

### 📂 What I Did:

* Loaded starter code in notebook
* Imported necessary libraries and SDKs
* Filled `INSERT HERE` sections to:

  * Define the function schema
  * Build the prompt for Gemini
  * Parse and print weather results from the function call

### 📌 Prompt Example:

```python
prompt = "What's the current weather in Tokyo and New York?"
```

### ✅ Output:

Gemini executed a structured **function call**, returning mock weather data for both cities using the provided schema.

---

## 🎬 Task 4: Describe Video Contents using Gemini

In this task, I completed notebook cells under **# Task 4** to analyze video input using Gemini.

### 🧩 Steps Taken:

* Loaded video into the notebook
* Used Gemini's **Flash 2.0 model** to generate descriptive outputs
* Prompts were tailored for:

  * Scene summary
  * Visual objects detection
  * Emotion and action tagging

### 📺 Video Used:

> *Provided sample video in the lab*

### 📌 Sample Prompt:

```python
prompt = "Describe the content of this video, including objects, actions, and overall tone."
```

### ✅ Gemini Output:

A detailed multi-sentence response covering:

* People, objects, and actions
* Background setting and mood
* Interpretive summary of message (ideal for video captioning/SEO)

---
## UI for APP
![genai image course 5](https://github.com/user-attachments/assets/e5303432-3302-431e-afa1-1c1ab0c30954)


## 🧠 Key Learnings

* **Text generation** via `curl` taught me the structure and authentication flow of Vertex AI API calls
* **Function calling** using Gemini allows structured and dynamic action execution with schema-based responses
* **Video content understanding** from Gemini Flash is highly usable for content tagging, summarization, and accessibility

---


## ✍️ Author

Written as part of the **#GenAIExchange Challenge** By (https://github.com/ayushiroully)
