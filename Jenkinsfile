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
             withCredentials([usernamePassword(credentialsId: 'PCF_LOGIN',
                     usernameVariable: 'thisisnikhil86@gmail.com', passwordVariable: 'Super@8515')]) {
    //available as an env variable, but will be masked if you try to print it out any which way
    sh 'echo $PASSWORD'
    echo "${env.USERNAME}"
}
    }
            }
        }
}
