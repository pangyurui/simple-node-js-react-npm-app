/* Requires the Docker Pipeline plugin */
pipeline {
    agent { docker { image 'node:20.11.1-alpine3.19' } }
    stages {
        stage('build') {
            steps {
                timeout(time: 1, unit: 'MINUTES') {
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
    post {
        always {
            echo 'this will always run'
        }
        success {
            echo 'this will run only if successful'
        }
        failure {
            echo 'this will run only if failed'
        }
        unstable {
            echo 'this will run only if the run was marked as unsatble'
        }
        changed {
            echo 'this will run only if the state of the pipeline has changed'
            echo 'for example, if the pipeline was previously failing but is now successful'
        }
    }
}