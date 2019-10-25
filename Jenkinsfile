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
                 sh 'cf api https://api.your-cf-installation.com --skip-ssl-validation
                 sh 'cf login -u thisisnikhil86@gmail.com -p Super@8515 -o nik -s development
}
    }
            }
        }
}
