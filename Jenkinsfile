pipeline {
    agent any
    stages {
        stage ('SCM') {
            steps {
                git branch: 'master', url: 'https://github.com/vamsibyramala/dicet_tv.git'
            }
        }
        stage ('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage ('Deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://13.126.108.68:8080/')], contextPath: 'test', war: '**/*.war'
            }
        }
    }
}
