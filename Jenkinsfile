pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh 'cd SampleWebApp mvn test'
            }
        }
        stage('Compile Build') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }
        
        stage('Deploy to Tomcat Web Server') {
            steps {
                
                deploy adapters: [tomcat9(credentialsId: 'ktomcatID', path: '', url: 'http://18.220.46.90:8080')], contextPath: 'app', war: '**/*.war'
        }
    }
}
}
