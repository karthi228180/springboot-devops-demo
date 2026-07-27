pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git url: 'https://github.com/karthi228180/springboot-devops-demo.git',
                    branch: 'main'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t springboot-demo:v1 .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8080:8080 springboot-demo:v1'
            }
        }
    }
}
