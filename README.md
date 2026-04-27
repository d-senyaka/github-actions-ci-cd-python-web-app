# 🚀 GitHub Actions CI/CD for Python Web App

A full Continuous Integration and Continuous Deployment (CI/CD) pipeline using **GitHub Actions** and **Render** to build, test, and deploy a simple Python Flask web app automatically on every push to the `main` branch.

---


## 🛠️ Tech Stack

- **Language**: Python 3.10
- **Framework**: Flask
- **Testing**: PyTest
- **CI/CD**: GitHub Actions
- **Hosting**: Render (Free Tier)

---

## 🧪 Features

- ✅ Automatically run tests on every push or pull request
- ✅ Automatically deploy to Render on successful tests
- ✅ Uses GitHub Secrets to protect deploy hooks
- ✅ Modular, clean setup for easy scaling and extensions

---

## 📂 Project Structure

```
my-flask-app/
├── app.py                # Flask application
├── test_app.py           # PyTest unit tests
├── requirements.txt      # Python dependencies
└── .github/
    └── workflows/
        └── ci.yml        # GitHub Actions CI/CD pipeline
```

---

## ⚙️ CI/CD Pipeline Workflow

GitHub Actions runs the following steps on each `push` or `pull_request`:

1. Checkout code
2. Set up Python 3.10
3. Install dependencies (`pip install -r requirements.txt`)
4. Run tests with PyTest
5. If successful, call the **Render Deploy Hook** stored in `RENDER_DEPLOY_HOOK` secret

```yaml
# .github/workflows/ci.yml
on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]
```

---

## 🧪 Testing Locally

```bash
# Install dependencies
pip install -r requirements.txt

# Run tests
pytest
```

---

## 📦 Deployment

This project is deployed to **Render** via an auto-generated deploy hook. The webhook is called only after all tests pass successfully.

🔐 The webhook URL is stored securely as a GitHub Actions Secret:
```
Name: RENDER_DEPLOY_HOOK
```

---

## 👨‍💻 Author

**Deshan Senanayake**  
📍 Colombo, Sri Lanka  
🎓 BSc (Hons) Artificial Intelligence & Data Science  
📚 Robert Gordon University (UK) @ Informatics Institute of Technology  
🔗 [GitHub](https://github.com/Deshan-Senanayake)

---

## 📘 License

This project is licensed under the MIT License.

---

## 📌 Badge

![CI](https://github.com/Deshan-Senanayake/github-actions-ci-cd-python-web-app/actions/workflows/ci.yml/badge.svg)
