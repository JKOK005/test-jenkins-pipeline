pipeline {
    agent { docker { image 'python:3.5.1' } }
    stages {
        stage('build') {
            steps {
                sh 'python --version'
                echo "asd"
            }
        }
    }
    
    post {
    	always {            
            emailext (
            	subject: "Jenkins Build ${currentBuild.currentResult}: Job ${env.JOB_NAME}",
			    to: 'johan.kok@u.nus.edu', 
			    body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}\n More info at: ${env.BUILD_URL}",
            )       
        }
    }
}
