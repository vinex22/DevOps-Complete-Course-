pipeline {
    agent {
        label 'vanilla'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
      
        stage('SonarQube Analysis') {
            steps {
                script {
                    def scannerHome = tool 'sq'
                    withSonarQubeEnv('sq') {
                        sh "${scannerHome}/bin/sonar-scanner"
                    }
                }
            }
        }
    }
}
