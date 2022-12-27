String branchName = "main"
String gitCredentials = "92a8aa18-0642-4ac8-a52d-cfe4834ee169"
String repoUrl = "git@github.com:thinkstop/jenkins-docker-git-first.git"


pipeline {
    agent any
        
    stages {
        stage('Setup') {
            steps {
                echo 'Creating work directory..'
                powershell 'New-Item -name "build" -ItemType "directory" -Force'
            }
        }
        stage('Clone') {
            steps {
                echo 'Cloning files from (repo: "' + branchName + '")'
                dir('build') {
                    git branch: branchName, url: repoUrl, credentialsId: gitCredentials
                }
                powershell 'Get-Location'
            }
        }
        stage('Compress') {
            steps {
                echo 'Compressing directory..'
                powershell 'Get-ChildItem -Path build | Compress-Archive -DestinationPath repo_compressed.zip -Force'
            }
        }
    }
}
