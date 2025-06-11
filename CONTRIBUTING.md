# 🤝 Contributing Guidelines

We're a group of curious minds and future data scientists working
together to turn data into meaningful impact.  
These guidelines help keep our work organized, consistent, and collaborative.

---

## 📁 1. Repository Structure

- **Main Branch**:  
  Do **not** commit directly to `main`. All changes must go through a
  pull request (PR).

- **Branches**:  
  Create a branch for each task using the format:

  ```text
  task-name
  ```

  _Example:_  
  `data-cleaning`

- **Project Folders**:
  - Each milestone has its own folder.
  - General summaries or key insights go in the top-level `README.md`.
  - The notes/meeting_minutes/ folder contains official meeting minutes.
  - Use the main notes/ folder for anything helpful or relevant to the team.

---

## 🔄 2. Workflow

### 1. Pull the latest changes from `main`

```bash
git checkout main
git pull origin main
```

### 2. Create a new branch

```bash
git checkout -b branch-name
```

### 3. Make your changes and commit

```bash
git add .
git commit -m "Short, clear message"
```

### 4. Push your branch

```bash
git push origin branch-name
```

> 💡 Tip: You can also push/pull using VS Code Source Control.

### 5. Open a pull request and request a review

### 6. Ensure your branch passes CI checks

### 7. Wait for approval before merging into `main`

---

## ✏️ 3. Commit Message Style

- Use **short, meaningful messages**
- Write in **present tense** (recommended)
- Examples:

  ```text
  Fix error in regression model
  Refactor notebook structure
  Add initial data visualization script
  ```

---

## 📊 4. Jupyter Notebooks

- Use **clear section headings** for structure
- Add **Markdown cells** to explain each major step
- Remove:
  - Sensitive data
  - Long or unnecessary outputs
- Naming convention:

  ```text
  topic_description.ipynb
  ```

  _Example:_  
  `air_pollution_analysis.ipynb`

---

## 🧼 5. Code Quality

- Follow the **PEP8** style guide
- Code must pass both **ruff** and **pylint**
- Use **clear, descriptive variable names**
- Create **functions** for reusable logic
- Add **comments** where helpful, especially for non-obvious logic.
- Include **docstrings** for all functions and classes to explain what they do.

---

## 🙌 6. Collaboration and Review

- Be respectful and constructive in reviews
- Remember: you're reviewing the work, **not** the person.
- Ask questions, no one is expected to know everything
- Use:
  - **GitHub Issues** or **Discussions** for bugs, tasks, and ideas
  - **Slack** or **WhatsApp** for quick coordination

- If you're going to miss a meeting, notify the team.  
  Meeting minutes are stored here:

  ```text
  notes/meeting_minutes/
  ```

---

## 🔐 7. File Naming and Organization

- Use **lowercase letters** and **underscores** (`snake_case`)
- Example:

  ```text
  aqi_data_cleaned.csv
  ```

- Keep your files in the correct **milestone folder**
- Do **not** upload temporary or unnecessary files

---

## ✅ Let’s work smart, stay organized, and build something amazing together! 🚀
