# GENAI_EXCHNAGE

This project is part of the [#GenAIExchange](https://cloud.google.com/training/generative-ai-exchange) program by Google Cloud. It demonstrates how to generate images from text using **Imagen**, and then analyze those images using **Gemini Flash** to generate a personalized message.

---

## 🚀 What This Project Does

- ✅ **Generates an image** of a custom bouquet using the `imagen-3.0-generate-002` model.
- ✅ **Analyzes the image** using `gemini-2.0-flash-001` and generates a **birthday wish** based on it.
- ✅ Uses **multimodal capabilities** (image + text) to simulate a real-world AI app flow.
- ✅ Supports **streaming output** from Gemini for a smoother experience.

---

## 🧱 Folder Structure

```bash
.
├── generate_image.py          # Code to call Imagen and save image
├── analyze_image.py          # Code to call Gemini with image input
├── bouquet.png               # Generated image (output)
├── requirements.txt
└── README.md
