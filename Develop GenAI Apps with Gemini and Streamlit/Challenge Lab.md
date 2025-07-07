
# 💬 Gemini Prompt Playground with Streamlit + Docker  
**Course 3: Develop GenAI Apps with Gemini and Streamlit — #GenAIExchange**

This project showcases my work from Course 3 of Google Cloud’s **#GenAIExchange** program. While the focus was on using **Streamlit + Gemini**, this repo contains:

- ✅ My **prompt experiments** using Gemini Pro  
- ✅ **Final Streamlit UI screenshot**  
- ✅ Docker setup for local deployment  
- ✅ Cloud Run deployment commands  
- ✅ Challenge-based Gemini prompts  

> 🧠 I explored prompt behavior, function calling concepts, and deployed the app using Docker to simulate a production environment.

---

## 🖼️ Final Streamlit UI
![blog - geminiapi streamlit app](https://github.com/user-attachments/assets/d36c58f5-4fbe-4427-b375-3bd044f642de)

## Recipe Suggestion
![blog - geminiapi streamlit app recipes1](https://github.com/user-attachments/assets/307ca892-7a81-4c27-8ecf-4b4e8ddcd62f)

## Recipe Ingredients Options
![blog- options to select](https://github.com/user-attachments/assets/b85ff057-44f5-43d5-abf3-1b2ffbb7631b)
## Food Prefrences 
![dropdown](https://github.com/user-attachments/assets/851c8d63-686d-4c0d-bb00-b2306199e8df)
## Cuisine Options
![dropdown2](https://github.com/user-attachments/assets/f0b662fb-12b4-4353-b816-88b3de27da05)

> *This UI was built with Streamlit, deployed via Docker & Cloud Run. It accepted prompt inputs and generated Gemini-based recipe suggestions.*

---

## 🧪 Challenge Tasks & My Implementation

### ✅ **Task 1: Use cURL to Test a Prompt with the API**

- Tool: **Vertex AI > JupyterLab**
- I executed a complex prompt using `curl` and Gemini API.

**🔹 Prompt Used**:

> I am a Chef. I need to create Japanese recipes for customers who want low sodium meals. However, I do not want to include recipes that use ingredients associated with a peanuts food allergy. I have ahi tuna, fresh ginger, and edamame in my kitchen and other ingredients. The customer wine preference is red. Please provide some for meal recommendations. For each recommendation include preparation instructions, time to prepare and the recipe title at the beginning of the response. Then include the wine paring for each recommendation. At the end of the recommendation provide the calories associated with the meal and the nutritional facts.

---

### ✅ **Task 2: Build a Streamlit App (chef.py)**

#### 🛠️ Steps I followed:
1. Cloned repo:  
   ```bash
   git clone https://github.com/GoogleCloudPlatform/generative-ai.git```


2. Navigated to: `generative-ai/gemini-streamlit-cloudrun`

3. Installed dependencies: `google-cloud-logging`

4. Downloaded starter Python file using:

   ```bash
   gsutil cp <Chef Python file path> .
   ```

5. Set up environment values:

   * `PROJECT_ID`
   * `REGION`
   * `LOCATION`

6. **Modified `chef.py`** to include Streamlit radio buttons for wine options:
   `Red`, `White`, and `None`

7. **Updated prompt template** in `chef.py`:

```python
prompt = f"""
I am a Chef. I need to create {cuisine} recipes for customers who want {dietary_preference} meals.
However, don't include recipes that use ingredients with the customer's {allergy} allergy.
I have {ingredient_1}, {ingredient_2}, and {ingredient_3} in my kitchen and other ingredients.
The customer's wine preference is {wine}.
Please provide meal recommendations.

For each recommendation, include:
- Preparation instructions
- Time to prepare
- Recipe title at the beginning of the response
- Wine pairing for each recommendation
- Calories and nutritional facts at the end
"""
```

8. Uploaded `chef.py` to GCS bucket:

```bash
gcloud storage cp chef.py gs://<your-bucket-name>
```

---

### ✅ **Task 3: Run and Test the Application**

1. Deployed and tested the Streamlit app locally.
2. Verified prompt customization and radio input handling.

---

### ✅ **Task 4: Modify Dockerfile and Push to Artifact Registry**

1. Set environment variables as required in challenge.

2. Created Artifact Registry repository:

```bash
gcloud artifacts repositories create <repo-name> \
  --repository-format=docker \
  --location=us-central1 \
  --description="Docker repo for GenAI app"
```

3. Built and submitted Docker image:

```bash
gcloud builds submit --tag \
gcr.io/$PROJECT_ID/genai-app
```

---

### ✅ **Task 5: Deploy to Cloud Run and Test**

Deployed the Dockerized app using:

```bash
gcloud run deploy genai-app \
  --image=$REGION-docker.pkg.dev/$PROJECT/$AR_REPO/$SERVICE_NAME \
  --platform managed \
  --region $REGION \
  --allow-unauthenticated \
  --set-env-vars PROJECT=$PROJECT
```

🎯 Once deployed, tested app via the provided Cloud Run URL.

---

## 🧠 Key Learnings

* Learned how to build prompt-driven UIs with Streamlit
* Understood how function variables can be captured via UI elements (radio/select)
* Got hands-on with Docker + Cloud Run deployment flows
* Experienced practical application of Gemini API for multi-input prompts

---

## 📚 References

* [Vertex AI with Gemini API](https://cloud.google.com/vertex-ai/docs/generative-ai)
* [Google Generative AI SDK](https://cloud.google.com/python/docs/reference/aiplatform/latest)
* [Streamlit Docs](https://docs.streamlit.io/)
* [Google Cloud Run](https://cloud.google.com/run)

---

## ✍️ Author

Created as part of the #GenAIExchange Challenge by **https://github.com/ayushiroully**

