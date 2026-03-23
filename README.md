# MRI Review Pro - Doctor's Usage Guide

This application is designed for doctors to review and validate AI-generated bounding box annotations for MRI scans.

## 🛠 Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/ViVi-Team/data-app.git
cd data-app
```

### 2. Initialize Git LFS
Since this project uses Git LFS for large image files, you must initialize it:
```bash
git lfs install
git lfs pull
```

Alternatively, you can download the results data manually using `gdown`:
```bash
pip install gdown
gdown --id 1fj7xZWUp9YyMwVSCcyEbbQHtCHOa08hC -O results.zip
unzip results.zip
```

### 3. Create a Virtual Environment (Recommended)
```bash
python3 -m venv .venv
source .venv/bin/activate  # On Windows use `.venv\Scripts\activate`
pip install -r requirements.txt
```

## 🚀 Getting Started

### 1. Launch the App
Run the following command in your terminal:
```bash
streamlit run review_app.py
```

### 2. Login
- Enter your **Name or ID** in the sidebar on the left.
- Click the **Login** button.

## 📋 How to Review

### 1. Select a Patient
Use the dropdown menu in the sidebar to select a patient from the list.

### 2. Navigate Slides
- Use the **⬅ Prev** and **Next ➡** buttons at the top to move through the MRI slides.
- You can also use your **Left** and **Right** arrow keys on your keyboard.

### 3. Review the Annotation
Each slide displays a **3-panel view**:
- **Left (Original)**: The raw MRI slide for reference.
- **Center (Gold Source)**: The original "Gold Standard" slide that the AI used for propagation.
- **Right (Perturbed)**: The AI-generated annotation on the current slide.

### 4. Make a Decision
- **Approve [A]**: If the AI-generated box on the right correctly identifies the region.
- **Reject [R]**: If the box is incorrect or misplaced.
- **Reset [C]**: Clear your decision for the current slide.

> [!NOTE]
> **Gold Standard slides** (the original manual annotations) will have the Approve/Reject buttons disabled, as they are already verified.

## 💾 Saving Your Work

### Automatic Saving
The app saves your decisions locally in your browser session as you work.

### Exporting Results
When you have finished your review:
1. Click **📊 Export Final Results (CSV)** in the sidebar to download your decisions.
2. If you need to pause and resume later on another machine, click **📥 Export Session (JSON)** to save your progress, and use the **📤 Import Session** box to restore it later.

---

## ⌨️ Keyboard Shortcuts
| Action | Key |
| :--- | :--- |
| **Approve** | `A` |
| **Reject** | `R` |
| **Reset** | `C` |
| **Previous Slide** | `Left Arrow` |
| **Next Slide** | `Right Arrow` |
