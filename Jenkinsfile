pipeline {
    agent {
        node 'slave01'
    }
    options {
        timestamps()
    }
    stages {
        stage('Pull image 1') {
            steps {
                script  {
                    def image = docker.image("python:3.6.12-alpine")
                    image.pull()
                }
            }
        }
        stage('Pull image 2') {
            steps {
                script {
                    try {
                        def image = docker.image("xx")
                        image.pull()
                    } catch (err) {
                        currentStage.result = 'FAILURE'
                        currentBuild.result = 'UNSTABLE'
                    }
                }
            }
        }
    }
}