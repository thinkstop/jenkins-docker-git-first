String branchName = "main"
String gitCredentials = "0be71c21-ec06-4eef-a1ba-bb804ef73342"
String repoUrl = "https://github.com/thinkstop/jenkins-docker-git-first.git"


pipeline {
    agent any
        
    stages {
        stage('Clone') {
            steps {
                echo 'cloning repo..'
                echo branchName
                echo repoUrl
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
