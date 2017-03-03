pipeline {
    agent any

    environment { 
        SOMETHING = 'foo'
    }

    stages {
        stage('Init') {
            steps {
                echo 'Hello World for ${env.SOMETHING}'
                echo "Build ${env.BUILD_ID}"
            }
        }

        stage('Post-Init') {
            environment { 
                SOMETHING = 'foo'
            }

            steps {
                echo 'Hello from Post-Init for ${env.SOMETHING}'
            }
        }

        stage('Approve') {
            steps {
                input message: 'Do you want to move to Docker build?', ok: 'Dockerize', 
                    parameters: [
                        string(defaultValue: '', description: 'Add notes here', name: 'Notes')
                    ]
            }
        }

        stage('Docker Test') {
            agent { docker 'openjdk:8-jre' } 
            steps {
                echo 'Hello, JDK'
                sh 'java -version'
            }
        }
    }
}