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
				sh "git add ."
				sh "git commit -m 'Message'"
				sh "git push origin master"
			}
        }
		
//		stage('Update GIT') {
//			steps {
//				script {
//					catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
//						withCredentials([usernamePassword(credentialsId: 'example-secure', passwordVariable: 'GIT_PASSWORD', usernameVariable: 'GIT_USERNAME')]) {
//							def encodedPassword = URLEncoder.encode("$GIT_PASSWORD",'UTF-8')
//							sh "git config user.email admin@example.com"
//							sh "git config user.name example"
//							sh "git add ."
//							sh "git commit -m 'Triggered Build: ${env.BUILD_NUMBER}'"
//							sh "git push https://${GIT_USERNAME}:${encodedPassword}@github.com/${GIT_USERNAME}/example.git"
//						}
//					}
//				}
//			}
//		}
    }
}