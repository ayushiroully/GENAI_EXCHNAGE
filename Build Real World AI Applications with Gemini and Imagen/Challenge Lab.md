This challenge introduced the power of combining text and visual understanding using Gemini and Imagen models — a critical capability for use cases like document analysis, visual storytelling, and personalized content generation.
This challenge involved two tasks:

✅ Task 1: Generate a Bouquet Image using Imagen

I created a Python function `generate_bouquet_image(prompt)` that uses the `imagen-3.0-generate-002` model to generate an image from a text prompt.

* 📥 Prompt used: *"Create an image containing a bouquet of 2 sunflowers and 3 roses"*
* 🖼️ Output: A high-quality bouquet image saved locally
* 🛠️ The function calls the model with basic authentication and saves the image using Python file I/O.

> 💡 *This demonstrated how generative vision models can translate text into visual concepts with precise control over details (like flower count).*



✅ Task 2: Analyze the Image and Generate a Birthday Wish with Gemini

Next, I implemented `analyze_bouquet_image(image_path)` using the `gemini-2.0-flash-001` model. This function:

* Takes the generated image as input
* Passes it to Gemini Flash along with a prompt to generate birthday wishes based on the image
* Uses streaming response so text outputs as it's being generated — great for responsiveness and UX

> 💡 *This step simulated a real-world multimodal use case: analyzing visuals and generating personalized messaging — like a birthday card powered by AI.*
