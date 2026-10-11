🚀 Python Web Application Deployment Using GitHub, Linux & Gunicorn

📌 Introduction

In this project, I deployed a Python web application on a Linux server using GitHub and Gunicorn. I uploaded the application files to GitHub, updated the server, installed the required packages, configured a Python virtual environment, and installed the application dependencies.

Finally, I installed Gunicorn to run the Python application as a web server and accessed the deployed application through the server's public IP address.

🏗️ Architecture Diagram

flowchart TD
    A[Developer] --> B[GitHub Repository]
    B -->|Git Clone| C[Linux Server EC2 / VPS]
    C --> D[Python3, Pip and Git]
    D --> E[Python Virtual Environment]
    E --> F[app.py]
    E --> G[requirements.txt]
    F --> H[Gunicorn]
    G --> H
    H --> I[Port 5000]
    I --> J[Web Browser]

📂 Project Structure

python-project/
├── app.py
├── requirements.txt
└── venv/

- app.py – Main Python application file.
- requirements.txt – Contains the required Python packages.
- venv/ – Isolated Python virtual environment.
- Gunicorn – Runs the Python application as a WSGI server.

🛠️ Step-by-Step Implementation

Step 1: Upload Project Files to GitHub

I uploaded the following files to my GitHub repository:

- "app.py"
- "requirements.txt"

Step 2: Update the Linux Server

sudo apt update
sudo apt upgrade -y

Step 3: Install Required Packages

sudo apt install -y python3 python3-pip git python3-venv

The packages installed were:

- Python3 – Runs Python applications.
- Python3-pip – Installs Python packages.
- Git – Clones the project from GitHub.
- Python3-venv – Creates a virtual environment.

Step 4: Clone the GitHub Repository

git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git

Navigate to the project directory:

cd YOUR-REPOSITORY

Step 5: Create and Activate a Virtual Environment

python3 -m venv venv
source venv/bin/activate

Verify the Python version:

python3 --version

Step 6: Update requirements.txt

I updated the required package version to "8.1.8" in the "requirements.txt" file.

For example, if the package was Flask:

Flask==8.1.8

Note: Confirm the actual package name and version used in your project. If "8.1.8" refers to a different package, keep that package's name in "requirements.txt".

Step 7: Install Project Dependencies

Upgrade pip:

python -m pip install --upgrade pip

Install the packages listed in "requirements.txt":

pip install -r requirements.txt

Step 8: Install Gunicorn

pip install gunicorn

Verify the installation:

gunicorn --version

Step 9: Run the Application Using Gunicorn

For a Flask application where "app.py" contains a Flask object named "app":

gunicorn --bind 0.0.0.0:5000 app:app

Explanation:

- "gunicorn" – Starts the Gunicorn server.
- "--bind 0.0.0.0:5000" – Listens on port 5000 on all network interfaces.
- "app:app" – The first "app" refers to "app.py"; the second "app" is the Flask application object.

Keep the process running while testing the application.

Step 10: Access the Application

Open the following URL in your browser:

http://YOUR-SERVER-PUBLIC-IP:5000

Make sure port "5000" is allowed in the server firewall or AWS Security Group, if applicable.

⚙️ Run Gunicorn in the Background

To run the application in the background for testing:

nohup gunicorn --bind 0.0.0.0:5000 app:app > app.log 2>&1 &

Check the process:

ps aux | grep gunicorn

View application logs:

tail -f app.log

For a production environment, configure Gunicorn with "systemd" and consider using Nginx as a reverse proxy.

✅ Project Outcome

- Uploaded Python application files to GitHub.
- Updated the Linux server.
- Installed Python3, pip, Git, and virtual environment support.
- Cloned the GitHub repository.
- Created and activated a Python virtual environment.
- Updated the required package version in "requirements.txt".
- Installed the project dependencies.
- Installed Gunicorn.
- Successfully deployed and accessed the Python application through the server's public IP and port.

🎯 Skills Learned

"Linux" · "Python" · "Git" · "GitHub" · "Virtual Environment" · "Pip" · "Gunicorn" · "Web Application Deployment"

👨‍💻 Conclusion

This hands-on project helped me understand the practical process of deploying a Python web application on a Linux server using GitHub, dependency management, virtual environments, and Gunicorn.

I look forward to learning more about automation, CI/CD pipelines, and DevOps tools.

#Python #Linux #GitHub #Gunicorn #AWS #DevOps #CloudComputing #HandsOnLearning
