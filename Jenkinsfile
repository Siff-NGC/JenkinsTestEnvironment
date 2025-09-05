//Jenkinsfile (Declarative Pipeline)

pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
				script {
					echo 'Fetching code.'
					git branch: "Ready/git", url: "https://github.com/Siff-NGC/JenkinsTestEnvironment.git"
				}
            }
        }
        stage('Build') {
            steps {
				script{
					echo 'Building code.'
				}
            }
        }
		stage('Test') {
            steps {
				script{
					echo 'Testing code.'
				}
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}