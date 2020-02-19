pipeline{

    agent any
     stages{
     
        stage('checkout'){
            steps{
                script{
                     // Clone repo
	                  git branch: 'master', 
	                  credentialsId: 'Git_login', 
	                  url: 'https://github.com/Abhijitkumar62/simple-java-maven-app.git'
                }
            }
        }
       stage ('build and test'){
            steps{
                script{
                def mvnHome = tool 'jenkins-maven'
                // sh "mvn clean install"
                sh "'${mvnHome}/bin/mvn' -Dintegration-tests.skip=true clean package"
                }   
            }
        }
        stage ('Email Notification') {
		script {
			mail bcc: '', body: 'aaaaa', cc: '', from: '', replyTo: '', subject: 'test Jenkin', to: 'abhijitkumar62@gmail.com'
		}
		     
	}
     }   
}      
