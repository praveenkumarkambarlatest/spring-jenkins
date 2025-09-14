pipeline {
    agent any
    tools {
        maven 'Apache Maven'
    }
    stages {
        stage("build") {
            steps {
                echo 'building the applications....'
                script {
                        if (isUnix()) {
                            sh 'mvn clean install'
                        } else {
                            bat 'mvn clean install'
                        }
                    }
            }
        }
        stage("test") {
            steps {
                echo 'testing the applications....'
            }
        }
        stage("deploy") {
            steps {
                echo 'deploying the applications....'
            }
        }
    }
}