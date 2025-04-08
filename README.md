# TASK 2: Create a Simple Jenkins Pipeline for CI/CD


1. command to install jenkins in docker container
>docker run -d -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home --name jenkins jenkins/jenkins:lts-jdk11

2. command to open log to see admin password
>docker logs jenkins

3. Create Github Repo

4. Clone the repo locally
https://github.com/bash4bags/Elevate_Labs_Task_2_08_04_2025

5. Created a Index.html file

6. Initialised git

>git init -b main

7. Pushed to repo

>git add .
git commit -m "message"
git push origin main

8. Created a Jenkinsfile in root directory

9. Put Jenkins to gitub

10. Create a pipeline jenkins
