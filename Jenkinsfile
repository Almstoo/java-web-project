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
                deploy adapters: [tomcat7(credentialsId: 'c2a553f3-ae73-4ccf-b4f3-9a258cc7f065', path: '', url: 'http://18.116.10.157:8080')], contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
