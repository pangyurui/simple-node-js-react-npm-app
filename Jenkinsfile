/* Requires the Docker Pipeline plugin */
pipeline {
    agent { docker { image 'node:20.11.1-alpine3.19' } }
    stages {
        stage('build') {
            steps {
                sh 'node --version'
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
}