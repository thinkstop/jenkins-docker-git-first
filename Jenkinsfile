String branchName = "main"
String gitCredentials = "0be71c21-ec06-4eef-a1ba-bb804ef73342"
String repoUrl = "https://github.com/thinkstop/jenkins-docker-git-first.git"


pipeline {
    agent any
        
    stages {
        stage('Setup') {
            steps {
                echo 'cloning repo..'
                echo branchName
                echo repoUrl
                echo 'Cloning files from (repo: "' + branchName + '")'
                powershell 'New-Item -name "build" -ItemType "directory" -Force'
            }
        }
        stage('Clone') {
            steps {
                echo 'Cloning..'
                dir('build') {
                    git branch: branchName, url: repoUrl, credentialsId: gitCredentials
                }
                powershell 'Get-Location'
            }
        }
        stage('Compress') {
            steps {
                echo 'Showing directory..'
                powershell 'Get-ChildItem -Path build | Compress-Archive -DestinationPath repo_compressed.zip -Force'
            }
        }
    }
}
