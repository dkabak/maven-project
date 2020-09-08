pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
                sh 'mvn clean package'
                sh 'docker build . -t tomcatwebapp:version1.0}'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}
