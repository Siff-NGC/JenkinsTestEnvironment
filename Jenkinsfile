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
					bat "\"${tool 'VS2022'}\\msbuild" Sample-Test1/Sample-Test1.sln /p:Configuration=Debug %MSBUILD_ARGS%"
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