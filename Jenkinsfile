pipeline {
    agent any 
    stages {
        stage('Build'){
            steps{
                sh 'mvn clean package'
                sh "docker build . -t tomcatwebapp:${env.BUILD_ID}"
            }
        }
        stage ('Deploy') {
            steps {

                withCredentials([[$class          : 'UsernamePasswordMultiBinding',
                                  credentialsId   : 'PCF_LOGIN',
                                  usernameVariable: 'thisisnikhil86@gmail.com',
                                  passwordVariable: 'Super@8515']]) {

                    bat "C:/Program Files/Cloud Foundry/cf login -a http://api.run.pivotal.io -u $USERNAME -p $PASSWORD"
		
                    bat "C:/Program Files/Cloud Foundry/cf push"
    }
            }
        }
}
