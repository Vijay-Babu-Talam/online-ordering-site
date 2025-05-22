pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Vijay-Babu-Talam/online-ordering-site.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("online-ordering-site")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 8083:80 --name ordering-container-ci online-ordering-site || true'
            }
        }
    }
}

