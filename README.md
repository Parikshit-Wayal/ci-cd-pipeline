# 🚀 Jenkins CI/CD Pipeline with SonarQube, Docker & Email Notifications

This project demonstrates a **complete CI pipeline using Jenkins (Pipeline as Code)** integrated with **GitHub Webhooks**, **SonarQube Quality Gates**, **Docker image build**, and **Email notifications**.

---

## 📌 CI/CD Architecture Flow


---

## 🧠 Pipeline Approach – Pipeline as Code

This project follows the **Pipeline as Code** approach:

- Jenkins job is configured as **“Pipeline script from SCM”**
- GitHub repository URL is provided in Jenkins
- GitHub credentials are stored securely in **Jenkins Global Credentials**
- Jenkins automatically fetches the `Jenkinsfile` from the repository
- All CI logic is version-controlled along with the application code

---

## ⚙️ Step-by-Step Pipeline Execution

---

## 1️⃣ Jenkins Setup & Login

Jenkins server is installed and running successfully.

![jenkins-login](https://github.com/user-attachments/assets/88d190b5-6039-4ad2-a156-aa2399bc84cc)

---

## 2️⃣ Jenkins Job Status Dashboard

Shows pipeline job status, build history, and execution results.

![jenkins-status](https://github.com/user-attachments/assets/6099c8f4-fe8a-4f79-8b72-c426eeb401de)

---

## 3️⃣ GitHub Webhook Configuration

GitHub webhook is configured to trigger Jenkins automatically on every **Git push**.

![webhook-testing](https://github.com/user-attachments/assets/d6ee2264-4d5c-445e-a78b-6eccbac86ad4)

✔ Webhook delivery successful  
✔ No manual build trigger required  

---

## 4️⃣ SonarQube Plugin Installed in Jenkins

SonarQube Scanner plugin is installed and configured in Jenkins.

![sonarcube_plugin-in_jenkins](https://github.com/user-attachments/assets/c41888af-ce2e-4ad4-a7d9-ea3a7d28b3b4)

---

## 5️⃣ SonarQube Authentication Using Token

A secure SonarQube token is generated and stored in Jenkins credentials.

![sonarcube-jenkin-token](https://github.com/user-attachments/assets/fce3d6a1-41c0-4bd5-afe4-04013327e53e)

✔ Token-based authentication  
✔ No credentials hardcoded in Jenkinsfile  

---

## 6️⃣ SonarQube Login & Project Dashboard

SonarQube server dashboard showing the configured project.

![sonarcube-login](https://github.com/user-attachments/assets/fe3f98b9-f35d-4e45-bd63-ac06c1b3cb4e)

---

## 7️⃣ Pipeline Triggered → SonarQube Analysis Executed

Pipeline automatically runs SonarQube analysis after code checkout and dependency installation.

![tested_SQ-via-pipeline triggerd](https://github.com/user-attachments/assets/b036f014-fcd6-45e2-af3b-595eb6e5fe86)

---

## 8️⃣ Quality Gate Passed (Successful Case)

When the Quality Gate passes:
- Pipeline continues
- Docker image is built
- Success email is sent

![gate_pass-success notification](https://github.com/user-attachments/assets/6d706bd5-03c3-41e0-8800-db0401b4470b)

---

## 9️⃣ Quality Gate Failed (Intentional Failure Test)

When application code is intentionally changed to introduce issues:
- SonarQube Quality Gate fails
- Pipeline is aborted
- Docker image build is skipped
- Failure email notification is sent

![tested-failed_by changing app js](https://github.com/user-attachments/assets/bb137436-7f31-4c2c-81bc-f7f47647b8a3)

---

## 🔟 Email Notification Configuration in Jenkins

Email notification is configured in Jenkins for build status alerts.

![configured-email_notify](https://github.com/user-attachments/assets/dc3ddeae-4d31-4c8b-a631-724c7d519fd8)

---

## 1️⃣1️⃣ Email Notification – Success Case

Success email received when pipeline completes successfully.

![notification-tested](https://github.com/user-attachments/assets/7d43dc72-a4fa-4e65-bd4a-0bef797a202c)

---

## 1️⃣2️⃣ Email Notification – Failure Case

Failure email received when Quality Gate fails or pipeline errors occur.

![get_notify-cause_failed](https://github.com/user-attachments/assets/1abf2ae2-b28e-4a8f-982d-230b53785306)

---

## 🔐 Secure & Configurable Setup

- GitHub credentials stored in Jenkins Credentials Manager
- SonarQube token managed securely
- Email recipients configured via environment variables
- SonarQube project key externalized
- No secrets hardcoded in the repository

---

## ⭐ Key Highlights (For Interview)

- Pipeline as Code using Jenkins
- GitHub webhook-based automation
- SonarQube Quality Gate enforcement
- Conditional Docker image build
- Secure credential management
- Automated email notifications

---

## ✅ Final Status

✔ End-to-end CI pipeline working  
✔ Quality gate enforced correctly  
✔ Notifications verified  
✔ Interview-ready project  

---

## 🔮 Future Enhancements (Optional)

- Switch `npm install` → `npm ci`
- Push Docker image to registry
- Add unit tests and coverage
- Parameterize Docker image name
