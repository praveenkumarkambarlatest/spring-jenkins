pipeline {
    agent any
    tools {
        maven 'Apache Maven'
    }
    parameters {
        choice(name: 'VERSION', choices: [1.1.0, 1.2.0, 1.3.0], ''),
        booleanParam(name: 'executeTest', defaultValue: true, description: '')
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
            when {
                expression {
                    params.executeTest
                }
            }
            steps {
                echo 'testing the applications....'
            }
        }
        stage("deploy") {
            steps {
                echo 'deploying the applications....'
                echo "deploying version ${params.VERSION}"
            }
        }
    }
}