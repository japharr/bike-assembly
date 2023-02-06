pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'rm -rf build'
                sh 'mkdir build'
                sh 'touch build/bike.txt'
                sh 'echo "chasis" >> build/bike.txt'
                sh 'echo "engine" >> build/bike.txt'
                sh 'echo "body" >> build/bike.txt'
            }
        }
        stage('Test') {
            steps {
                sh 'test -f build/bike.txt'
                sh 'grep "chasis" build/bike.txt'
                sh 'grep "engine" build/bike.txt'
                sh 'grep "body" build/bike.txt'
            }
        }
        stage('Publish') {
            steps {
                archiveArtifacts artifacts: 'build/'
            }
        }
    }
}
