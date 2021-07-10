pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh "mvn clean package"
            }
        }
        stage('Deploy') {
            steps {
                deploy adapters: [tomcat7(credentialsId: '38fa7925-9370-4e7c-85c0-db6ef2af6c1e', path: '', 
                url: 'http://3.133.126.36:8080')], 
                contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
