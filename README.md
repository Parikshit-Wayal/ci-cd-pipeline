# 🚀 Jenkins CI/CD Pipeline with SonarQube, Docker & Email Notifications  


👉 **Whenever a developer pushes code to GitHub, Jenkins automatically starts, checks code quality using SonarQube, builds a Docker image only if the code is good, and sends email notifications.**

Everything happens automatically.

---

## 📌 CI/CD Architecture Flow


https://github.com/user-attachments/assets/1f21ab68-93b2-4cef-ae09-29c9d9c3e19b


### Simple Flow Explanation:
1. Developer pushes code to **GitHub**
2. GitHub **Webhook** triggers Jenkins
3. Jenkins reads the `Jenkinsfile`
4. SonarQube checks code quality
5. Quality Gate result is evaluated
6. If **PASS** → Docker image is built
7. Email notification is sent

---

## ⚙️ Step-by-Step Pipeline Execution (Easy Explanation)

---

## 1️⃣ Jenkins Setup & Login

Jenkins server is installed and running successfully.

![jenkins-login](https://github.com/user-attachments/assets/88d190b5-6039-4ad2-a156-aa2399bc84cc)

👉 Jenkins is the main tool that runs the entire CI pipeline.

---

## 2️⃣ Jenkins Job Status Dashboard

Jenkins dashboard shows:

- Pipeline job status


![jenkins-status](https://github.com/user-attachments/assets/6099c8f4-fe8a-4f79-8b72-c426eeb401de)

👉 Helps in monitoring and troubleshooting builds.

---

## 3️⃣ GitHub Webhook Configuration

GitHub webhook is configured to trigger Jenkins automatically on every **git push**.

![webhook-testing](https://github.com/user-attachments/assets/d6ee2264-4d5c-445e-a78b-6eccbac86ad4)

✔ Automatic build trigger  
✔ No manual intervention  

---

## 4️⃣ SonarQube Plugin Installed in Jenkins

SonarQube Scanner plugin is installed in Jenkins.

![sonarcube_plugin-in_jenkins](https://github.com/user-attachments/assets/c41888af-ce2e-4ad4-a7d9-ea3a7d28b3b4)

👉 Allows Jenkins to analyze code quality.

---

## 5️⃣ SonarQube Authentication Using Token

A secure SonarQube token is generated and stored in Jenkins credentials.

![sonarcube-jenkin-token](https://github.com/user-attachments/assets/652a6c47-41f3-460a-b879-7a2504c890ad)

✔ Secure authentication  
✔ No hardcoded credentials  

---

## 6️⃣ SonarQube Login & Project Dashboard

SonarQube dashboard showing the project details.

![sonarcube-login](https://github.com/user-attachments/assets/fe3f98b9-f35d-4e45-bd63-ac06c1b3cb4e)

👉 Displays bugs, code smells, vulnerabilities, and quality gate status.

---

## 7️⃣ Pipeline Triggered → SonarQube Analysis Executed

When code is pushed:

- Jenkins pulls the code
- Installs dependencies
- Runs SonarQube analysis automatically

![tested_SQ-via-pipeline triggerd](https://github.com/user-attachments/assets/b036f014-fcd6-45e2-af3b-595eb6e5fe86)

👉 Jenkins waits for the Quality Gate result.

---

## 8️⃣ Quality Gate Passed (Success Case)

If code quality is good:

✔ Quality Gate passes  
✔ Docker image is built  
✔ Success email is sent  

![gate_pass-success notification](https://github.com/user-attachments/assets/6d706bd5-03c3-41e0-8800-db0401b4470b)

---

## 9️⃣ Quality Gate Failed (Intentional Failure Test)

If bad code is pushed:

❌ Quality Gate fails  
❌ Pipeline stops  
❌ Docker build skipped  
❌ Failure email sent  

![tested-failed_by changing app js](https://github.com/user-attachments/assets/bb137436-7f31-4c2c-81bc-f7f47647b8a3)

👉 Prevents bad code from moving forward.

---

## 🔟 Email Notification Configuration in Jenkins

Email notifications are configured in Jenkins.

![configured-email_notify](https://github.com/user-attachments/assets/dc3ddeae-4d31-4c8b-a631-724c7d519fd8)

👉 Jenkins sends automatic build status emails.

---

## 1️⃣1️⃣ Email Notification – Success Case

Success email received after pipeline completion.

![notification-tested](https://github.com/user-attachments/assets/7d43dc72-a4fa-4e65-bd4a-0bef797a202c)

---

## 1️⃣2️⃣ Email Notification – Failure Case

Failure email received when pipeline fails.

![get_notify-cause_failed](https://github.com/user-attachments/assets/1abf2ae2-b28e-4a8f-982d-230b53785306)

---

## 🔐 Secure & Configurable Setup

- GitHub credentials stored securely in Jenkins
- SonarQube token managed via credentials
- No secrets hardcoded in Jenkinsfile
- Email IDs and project keys are configurable

