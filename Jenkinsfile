//Jenkinsfile (Declarative Pipeline)

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
				script {
					echo 'Fetching code.'
					git branch: "Ready/git", url: "https://github.com/Siff-NGC/JenkinsTestEnvironment.git"
				}
            }
        }
        stage('Test') {
            steps {
				script{
					ls
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