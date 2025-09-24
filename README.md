# Basic Spring Boot Application Deployment CI/CD pipeline with Jenkins

This repository demonstrates a basic Jenkins pipeline to build, test, and deploy a Spring Boot application.

## Prerequisites
- Java 17+
- Maven 3+
- Jenkins server
- GitHub repository (this repo)

## Steps to Run

### 1. Clone the Repository
```bash
git clone https://github.com/Kiran-Komroju/el_task2
````

### 2. Jenkins Setup

1. Install Jenkins on your server
2. Access Jenkins at: `http://localhost:8080`
3. Install suggested plugins.
4. Configure tools:

   * **JDK 17**
   * **Maven 3
### 3. Jenkins Pipeline

This project includes a `Jenkinsfile` with the following stages:

* **Checkout** – Pulls latest code from GitHub
* **Build** – Compiles Spring Boot application
* **Test** – Runs unit tests
* **Deploy** – Deploys the application as a JAR

### 4. GitHub Webhook

Set up a webhook in your GitHub repository to trigger Jenkins on every push:

* URL: `http://<jenkins-server-ip>:8081/github-webhook/`
* Content type: `application/json`
* Event: `push`

### 5. Run the Pipeline

1. Push changes to the `main` branch.
2. Jenkins will automatically start the pipeline.
3. After successful deployment, check the running application:

   ```bash
   curl http://<jenkins-server-ip>:8081
   ```

## Project Structure

```
.
├── src/               # Spring Boot source code
├── target/            # Compiled artifacts (generated after build)
├── Jenkinsfile        # Jenkins pipeline definition
├── pom.xml            # Maven build file
└── README.md          # Project documentation
```

👤 Author
Kiran Komroju
GitHub: kirankomroju
