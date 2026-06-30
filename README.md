# java-webapp
life cycle of maven 
```bash
validate
     │
compile
     │
test
     │
package
     │
verify
     │
install
     │
deploy
```
---------------------
## Install git 
```bash
git config --global user.name "Your Name"
```
```bash
git config --global user.email "your-email@example.com"
```
```bash
git clone https://github.com/alskill/java-webapp.git
```
```bash
git add .
```
```bash
git commit -m "Initial commit"
```
```bash
git push origin main
```
-----------
## create jenkins server
``` bash
pwd
```
it should be folder on laptop where project is stored
You should see:

/Users/almal/OneDrive/Desktop/devops

## step 1 : create the Jenkins folder:
```bash
mkdir jenkins
```
```bash
cd jenkins
```
## Step 2: Create a Docker volume

This stores Jenkins data permanently.
```bash
docker volume create jenkins_home
````
Check:
```bash
docker volume ls
```
## Step 3: Pull the Jenkins LTS image
```bash
docker pull jenkins/jenkins:lts
```
Verify:
```bash
docker images
```
## Step 4: Run the Jenkins container
```bash
docker run -d \
--name jenkins \
-p 8080:8080 \
-p 50000:50000 \
-v jenkins_home:/var/jenkins_home \
jenkins/jenkins:lts

```
## Step 5: Verify the container
```bash
docker ps
```
You should see:
```bash
CONTAINER ID   IMAGE                  STATUS
xxxxxxxx       jenkins/jenkins:lts    Up
```
## Step 6: Open Jenkins
Open your browser:
```bash
http://localhost:8080
```
You'll see:
```bash
Unlock Jenkins
```
## Step 7: Get the initial administrator password

```bash
docker exec jenkins -it /bin/bash
```
```bash
cat /var/jenkins_home/secrets/initialAdminPassword
```
Copy the password.
## Step 8: Unlock Jenkins

Paste the password.

Click Continue.

## Step 9: dont Install plugins

Click: continue without install
## Step 10: Create the first admin user

Example:

Username: admin

Password: admin123 (choose a stronger password for real use)

Full Name: Your name

Email: Your email

Click Save and Continue.





























