//Jenkinsfile (Declarative Pipeline)

pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
				script {
					echo 'Fetching code.'
					//git branch: "$BRANCH_NAME", url: "https://github.com/Siff-NGC/JenkinsTestEnvironment.git"
					checkout scmGit(branches: [[name: '**']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Siff-NGC/JenkinsTestEnvironment.git']])
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
                echo 'Deploying binaries.'
				sh "cat 'version: $BUILD_NUMBER'" > version.txt
//				sh "git add ."
//				sh "git commit -m 'Message'"
//				sh "git push origin Master"
			}
        }
    }
}