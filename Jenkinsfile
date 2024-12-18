pipeline {
    agent any

    stages {
        stage('without docker') { // เปลี่ยนชื่อ stage ให้ชัดเจน
            steps {
                sh '''
                echo "Running without Docker"
                ls -la
                touch container-no.txt
                '''
            }
        }

        stage('w/ docker') { // เปลี่ยนชื่อ stage เพื่อให้ชัดเจน
            agent {
                docker {
                    image 'node:18-alpine'
                }
            }
            steps {
                sh '''
                echo "Running with Docker"
                ls -la
                touch container-yes.txt
                '''
            }
        }
    }
}
