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
             withCredentials([usernameColonPassword(credentialsId: 'PCF_LOGIN', variable: 'PCF_LOGIN')]) {
    // some block
                 sh 'cf login -a http://api.run.pivotal.io -u $USERNAME -p $PASSWORD"
                 sh 'cf login -u thisisnikhil86@gmail.com -p Super@8515 -o nik -s development
}
    }
            }
        }
}
