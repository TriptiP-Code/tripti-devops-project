# Project 1 - Jenkins + Docker + Python App
This project demonstrates a simple DevOps pipeline...

1. 🐍 Python App (Flask)
The app is a simple web application that returns:
Hello, Tripti! Your DevOps pipeline is working!
<img width="1914" height="315" alt="image" src="https://github.com/user-attachments/assets/d139477d-f927-44df-ba01-99ed266199b0" />

2. 🐳 Docker Setup
The Dockerfile:
1.Uses Python 3.10 slim
2.Installs Flask from requirements.txt
3.Exposes port 5000
4.Runs the Flask app

Container 
<img width="1891" height="921" alt="image" src="https://github.com/user-attachments/assets/f99b7f8d-efbf-4c19-aff8-7068b0af21dd" />
Image created
<img width="1896" height="976" alt="image" src="https://github.com/user-attachments/assets/f576e89b-e0c6-45a5-8d1a-7618fcebb6b8" />


4. 👷 Jenkins Pipeline (CI/CD)
The Jenkinsfile performs:
1️⃣ Checkout source code
2️⃣ Build Docker image
3️⃣ Run the container
4️⃣ Test that the app is running

Jenkins pipeline 
<img width="1918" height="1065" alt="image" src="https://github.com/user-attachments/assets/601dbb06-9e02-4510-916b-97370bc87e90" />

Successful job run
<img width="1904" height="1014" alt="image" src="https://github.com/user-attachments/assets/6797f8d0-38e0-4337-91a8-a0215ea2e5cc" />

5. Troubleshooting
Got issue with docker mapping , I initially mapped docker as 5000:8080 , but later found that already 8080 port is being used by jenkins locally
5000:8000
Outside (host): 5000
Inside (container): 8080

Some Command issue in jenkins pipeline , as using personal desktop (OS : windows) to run jenkins ,there is no sh (Bash shell) available by default, so Jenkins gave an error like:
'sh' is not recognized as an internal or external command
therefore I changed all sh steps to bat, like:
bat 'echo Building Docker image...'






