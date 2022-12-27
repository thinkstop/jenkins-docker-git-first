String branchName = env.BRANCH_NAME
//String gitCredentials = "CREDENTIAL_ID"
String repoUrl = "https://github.com/thinkstop/jenkins-docker-git-first.git"


pipeline {
    agent any
        
    stages {
        stage('Clone') {
            steps {
                echo 'cloning repo..'
                sh 'mkdir build'
                echo 'Cloning files from (repo: "' + branchName + '")'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
                git branch: branchName, url: repoUrl
            }
        }
        stage('Show') {
            steps {
                echo 'Showing directory..'
                sh 'ls build'
            }
        }
    }
}
