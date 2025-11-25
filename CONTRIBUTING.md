# **Contributing to Meow AI**

This document establishes the **Law of the Repo**. All team members must follow these rules to ensure the project moves fast and stays clean.

## **1\. 🧪 The Golden Rule: Experiment Tracking**

**CRITICAL:** We are doing Science, not just coding. Every time you train a model, you **MUST** log it.

### **How to Log**

Copy the line below and add it to experiments.csv (or our shared Google Sheet) after every run.

| Run ID | Model | Image Size | Epochs | Learning Rate | F1-Score | Notes |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| exp\_01 | ResNet50 | 224x224 | 10 | 0.001 | 0.72 | Baseline run, overfits after epoch 5 |
| exp\_02 | BLIP-2 (LoRA) | 224x224 | 5 | 0.0001 | 0.85 | Great textual explanations, slow training |

Why?  
When we write the Final Report in January, we will simply turn this table into the "Results" section. If you don't log it, it didn't happen.

## **2\. 🐍 Python Code Style**

We follow simple rules to keep code readable:

* **Variables:** Use snake\_case for variables/functions (e.g., load\_image, model\_weights).  
* **Classes:** Use PascalCase for classes (e.g., VisionEncoder, EmotionClassifier).  
* **Docstrings:** Every function MUST have a 1-line explanation.  
  def get\_heatmap(image, model):  
      """Generates a Grad-CAM heatmap for the given image."""  
      \# code...

* **No Magic Numbers:** Don't write 224 everywhere. Define IMG\_SIZE \= 224 at the top of the file.

## **3\. 💾 Git Commit Messages**

Do not write commits like "fix" or "update". Use this format:

\[CATEGORY\] Short description

**Categories:**

* \[FEAT\]: New feature (e.g., "Added Grad-CAM function")  
* \[FIX\]: Bug fix (e.g., "Fixed tensor shape error in train.py")  
* \[DOCS\]: Documentation (e.g., "Updated README")  
* \[EXP\]: Experiment related (e.g., "Added config for Qwen-VL run")

Example:  
git commit \-m "\[FEAT\] Added Streamlit file uploader"

## **4\. 🚀 Workflow Protocol (The "Main" Protection)**

1. **Never push directly to main** if you are unsure.  
2. Create a branch: git checkout \-b feature/my-new-feature  
3. Work on your branch.  
4. When done, merge or create a Pull Request.

## **5\. ⚠️ Definition of Done (DoD)**

A task is not "Done" until:

1. The code runs without error.  
2. Unnecessary print() statements are removed.  
3. The requirements.txt is updated (if you installed new libraries).