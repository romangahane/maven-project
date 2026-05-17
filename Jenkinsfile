pipeline {

    agent {
        label 'DevServer'
    }

    tools {
        maven 'mymeven'
    }

    environment {
        NAME = "Roman"
    }

    parameters {
        string(name: 'LASTNAME', defaultValue: 'Gahane')
    }

    stages {

        stage('build') {
            steps {
                sh 'mvn clean package'
                echo "Hello $NAME ${params.LASTNAME}"
            }

            post {
                success {
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }

        stage('test') {

            parallel {

                stage('testA') {
                    steps {
                        echo "This is test"
                    }
                }

                stage('testB') {
                    steps {
                        echo "This is test B"
                    }
                }
            }

            post {
                success {
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}