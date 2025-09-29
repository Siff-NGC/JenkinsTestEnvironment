//Jenkinsfile (Declarative Pipeline)

pipeline {
    agent any

    stages {
        
		
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
                echo 'Deploying binaries.'
				sh "echo Version: $BUILD_NUMBER > version.txt"
				sh "git add ."
				sh "git commit -m '$BUILD_NUMBER'"
//				sh "git push origin $BRANCH_NAME:Master"
				sh "git push origin HEAD:Master"
			}
        }
    }

}
