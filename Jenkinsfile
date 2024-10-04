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
              deploy adapters: [tomcat9(path: '', url: 'http://3.21.33.78:8080')], contextPath: 'mm', war: '**/*.war'
        }
    }
}
}
