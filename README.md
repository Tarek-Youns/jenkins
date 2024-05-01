# Prerequsets
EC2 instance on AWS
Jenkins
GitHub account
Git installed on the Jenkins server
GitFlow for later tasks
# Prepare GitHub Repository
Initialize the repository with a README.md, and ensure the repository contains at least two branches:
develop for ongoing development.
master (or main) for stable releases.
# push jenkins file 
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
# Plugin
Configure Jenkins to connect to GitHub:
Go to "Manage Jenkins" > "Manage Plugins" > "Available" and install "GitHub Integration Plugin".
Set up credentials in Jenkins for GitHub (username and token).
# Webhooks 
Add a new webhook:
Payload URL: http://:8080/github-webhook/
Content type: application/json
Select "Just the push event".
Ensure the webhook is active
# Validation
Push a change to the develop branch and verify Jenkins triggers a build.
# Author 
Tarek-Youns 
