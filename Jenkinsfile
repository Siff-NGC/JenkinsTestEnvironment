//Jenkinsfile (Declarative Pipeline)

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
				script {
					echo 'Fetching code.'
					git clone 'https://github.com/Siff-NGC/JenkinsTestEnvironment.git'
				}
            }
        }
        stage('Test') {
            steps {
                ls
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}