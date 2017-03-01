pipeline {
    agent any
    stages {
        stage('Init') {
            steps {
                echo 'Hello World'
                echo "Build {env.BUILD_ID}"
            }
        }

        stage('Post-Init') {
            steps {
                echo 'Hello from Post-Init'
            }
        }
    }
}