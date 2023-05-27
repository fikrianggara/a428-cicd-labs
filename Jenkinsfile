node {
    stage('Build') {
        docker.image('node:16-buster-slim').inside('-p 3000:3000') {
            sh 'npm install'
        }
    }

    stage('Test') {
        steps {
            sh "chmod +x -R ${env.WORKSPACE}"
            sh './jenkins/scripts/test.sh'
        }
    }
}