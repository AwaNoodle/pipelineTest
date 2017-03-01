pipeline {
    agent any
    stages {
        stage('Init') {
            steps {
                echo 'Hello World'
                echo 'Hello Other World'
            }
        }

        stage('Post-Init') {
            steps {
                echo 'Hello from Post-Init'
            }
        }
    }
}